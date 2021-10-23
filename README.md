# How npm link works with different dependency combinations
*tldr* linked packages should install their own dependencies so that they have access to them when linked. 

In NPM v7, theres a bug that prevents npm from installing linked package dependencies like you expect and like it did in NPM v6. The workaround is to install those dependencies manually. This can be done post install by manually cding into the linked dependency in the `node_modules` folder and `npm install`ing. Or, this can be done with docker multistage builds by copying the src and its node_modules to the destination project. 

Additional notes: 
- Peer deps are automatically installed like regular dependencies in NPM v7.

## Resources 
- https://github.com/npm/cli/issues/2339#issuecomment-880112661
- https://github.com/npm/cli/issues/2339#issuecomment-917355309
- https://github.com/npm/cli/issues/2339#issuecomment-940158337