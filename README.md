# Smoler pong
So i've tried to make a pretty small pong game for linux before and the [results](https://github.com/g3rwy/smol-pong) were not that bad, less than 10KB of binary.

Previously it was written in very C looking C++ because i struggled with getting it to work with something else than std::chrono, but i managed to fix it and do some pretty cool stuff.
- So ive rewritten entire thing to be all in C, still using X11 so you are only able to play this on Linux (or maybe Windows's WSL if they figure out stable X11 implementation)
- My strategy this time is not to compile a final product but provide a C script that will actually compile itself, yeah it turns out that you can basically put a small shell script before C to do something for you, its wrapped around `#if 0` macro so that it does not exist in our C file after preprocessing and compiler does not get confused
- I've minified all the variables, couldn't do anything about the functions from X11 unfortunately but i tried using as little as i could
- Of course you can probably make it even smaller, im not an expert i just like to experiment, but im pretty happy with final product
- The compiled binary should be cached in /tmp/ so that every time you execute the c file it does not compile it over and over again, but compile it once and for your entire session it should be stored in tmp folder

  ## Usage
So overall entire thing is inside that small 3.8KB c file, it might feel wrong to do but all you need to do is to execute it like so `./smoler_pong.c`, of course if it does not work or you are unable to do it, remember to give it executable flag with `chmod +x smoler_pong.c` that should do it. Of course you do need to have X11 installed to make it work, duh
