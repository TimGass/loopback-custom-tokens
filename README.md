# LoopBack Custom Tokens

This is a clone and slight alteration of LoopBack. All credit goes to original authors. I made small changes based off of a variety of solutions from the internet and tweaked my own support for custom tokens, since it appears the original authors of LoopBack are no longer working on new releases and pull requests. All works are filed under the original MIT license. Feel free to contribute or clone. Also, feel free to message me, if you feel in any way this infringes on your work.

The original repo and instructions can be found at: (https://github.com/strongloop/loopback).

### Usage of Custom tokens

It's fairly simple. I set it up to specifically refer to the token model by name, after it is built by using loopback.token. This should simply be passed as a string of the name of the token as defined in the model.json file, typically found in the common folder. This is not an incredibly complex problem or solution, however it seems that the original authors will not integrate it so I am putting it out there. Without such a patch, the code cannot run custom token models for authentication purposes. This makes more complex tokens unusable in the standard codebase of LoopBack.

In server/server.js add a line similar to this to the top of file, but below the library importation:

```
app.use(loopback.token({
    model: 'INSERT CUSTOM TOKEN MODEL NAME HERE'
}));
```
