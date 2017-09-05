# Sheperd Dog game

Created using the base code 0 by Rahul Balakrishnan <rbalakr1>
Find the original design document @ http://graphics.cs.cmu.edu/courses/15-466-f17/game0-designs/hungyuc/

You are a sheperd dog. You have the smartest bunch of sheep in the world to guard. The sheep are trying to escape and runaway from home.
If a sheep reaches the brown boundary you it is game over.
As the sheep run they lose weight and gain muscle mass... i.e they become faster.
Life is tough being a dog.

## Mechanics

 - Control the dog with the mouse
 - The sheep will change direction upon collision to move away from the most recent collision
 - Be carefull about the direction in which you touch a sheep. You will goad it to go it that direction.
   NOTE: This a change from the original design document which did not incorporate this. It caused the dog to get occluded.
   After some play testing the current version was chosen.
 - Score is displayed at the end of the game. With a prompt to click to continue.
 - The sheeps get faster with time

## Developer Notes

 The game has been tested on linux platform with GLSL version 3.2 ES on a radeon graphics card.
 I have achieved a high score of 19.. The game is hard.

## Requirements

 - glm
 - libSDL2
 - modern C++ compiler

On Linux or OSX these requirements should be available from your package manager without too much hassle.

## Building

### Linux
```
  g++ -std=c++11 -g -Wall -Werror -o main main.cpp Draw.cpp `sdl2-config --cflags --libs` -lGL
```
or:
```
  make
```

### OSX
```
  clang++ -g -Wall -Werror -o main main.cpp Draw.cpp `sdl2-config --cflags --libs`
```
or:
```
  make
```

### Windows

Before building, clone [kit-libs-win](https://github.com/ixchow/kit-libs-win) into the `kit-libs-win` subdirectory:
```
  git clone https://github.com/ixchow/kit-libs-win
```
Now you can:
```
  nmake -f Makefile.win
```
or:
```
  cl.exe /EHsc /W3 /WX /MD /Ikit-libs-win\out\include /Ikit-libs-win\out\include\SDL2 main.cpp Draw.cpp gl_shims.cpp /link /SUBSYSTEM:CONSOLE /LIBPATH:kit-libs-win\out\lib SDL2main.lib SDL2.lib OpenGL32.lib
  copy kit-libs-win\out\dist\SDL2.dll .
```

