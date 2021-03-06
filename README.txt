JediAcademyLinux
================

Jedi Knight III: Jedi Academy (Single Player Linux Port).
https://github.com/xLAva/JediAcademyLinux

The current state is playable without any major problems.
I didn't play the whole game yet, but I tested at least more than half of the levels. 


Binary

If you just want to play the game without compiling anything, the binary files are located here: "code/Release/".
The binary files are not build or tested to run on every Linux system, but they should work on Ubuntu 12.10.
I just wanted to add a little short cut.

The following files are needed to run the game:
- jasp
- jagamex86.so

In order to start Jedi Academy, the "base" folder from your original game has to be copied into the folder of the Linux binary files.
Be sure to mark "jasp" as executable and start the game with it.

For those not having the Steam version: you'll need the 1.01 update from here http://www.lucasarts.com/support/update/jediacademy.html 

Example:
~/jedioutcast/Release/jasp
~/jedioutcast/Release/jagamex86.so
~/jedioutcast/Release/base/

Needed libraries on Ubuntu 12.10 32bit:
sudo apt-get install libopenal1 zlib1g-dev

Needed libraries on Ubuntu 12.10 64bit:
sudo apt-get install ia32-libs libxxf86dga1:i386 zlib1g-dev:i386


Development

I used Code:Blocks as starting point for this port.
The whole compile process is based on it, but I think it should be pretty easy to add Makefiles or other compiling structures.
The source code is compiled with GCC.

My development system: Ubuntu 12.10 64bit
- I'm using a 64bit system, but this port is still a 32 bit program!

Needed development libraries (and codeblocks):
sudo apt-get install codeblocks g++-multilib libgl1-mesa-dev:i386 libxxf86dga-dev:i386 libxrandr-dev:i386 libopenal-dev:i386


Known Issues:

- multi-monitor handling is still experimental
- some font rendering issues with the Intel Mesa driver (on my test machine)
- input handling in window mode is not perfect


Widescreen Feature:

This is the only thing I changed from the original code to improve the gaming experience.
- added some tweaks for widescreen support (show more content left and right instead of cutting content from top and bottom)
- if you want to play in your native monitor resolution you have to choose the following option "2048x1536". I change this to the current resolution of the main monitor during OpenGL start up.


Porting Notes

This was a fast port, so don't be surprised to see some bad hacks in place.
The first goal was to get it to run. Making it better is the next step.
I share the code now (in it's current shape), because I know you want to play with it and maybe help out.

There is still a lot of work left to do:
- CLEANUP: I have a lot of porting helpers in place (comments and other stuff)
- stay closer to the original code: play with compiler flags to avoid/revert some bigger changes
- make my widescreen tweaks optional


Feel free to contact me: jochen.leopold@model-view.com
