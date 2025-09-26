# Chipwits-C

A reimplementation in C of the Classic Mac Game ChipWits, to run on slightly more modern 68K Mac Computers.

See other documentation in this folder.  Apologies - I haven't been as diligent as I should in keeping the documentation up to date.

## Summary

ChipWits is a programmable robot simulation originally developed in Forth, in the 1980s, for the original Macintosh computers (128k through to Mac Plus) and for the Commodore 64. Players write simple programs in a simple programming language to control a robot navigating a grid world filled with energy pods, pies, walls, and goals. This restoration ports the original Forth logic to modular C code compatible with Think C on classic Macintosh systems, preserving gameplay whilst (hopefully) enabling maintainable, future-proof development (using tools like [Pomme](https://github.com/jorio/Pomme) to build on modern computers).

## Build Instructions

Eventually - it doesn't yet work.  The resource file hasn't been completed, and the code is not yet complete.

### Requirements

* System: Classic Macintosh (System 6 or 7 recommended)
* Compiler: Think C 5.0 or later
* Memory: 1MB minimum
* Graphics: Any Macintosh with 1bit display support

### Steps

* Open Think C and create a new project.
* Add all .c and .h files listed above.
* Use ResEdit to create the resource fork and it to the newly created project.
* Ensure resource.h is included in every module that uses GetResource() or dialog IDs.

Build and run.  With fingers very much crossed.

## Attribution

Chipwits is copyright © 1984-2024 by ChipWits, Inc and was originally written in Mac Forth.  It was open sourced in 2024 and the source code made available [on GitHub](https://github.com/chipwits/chipwits-forth). This port to C is heavily based on the original Forth source code, and reuses the resource assets from the original game.

- "ChipWits, copyright 1984, DISCOURSE, Inc., All rights reserved"
- "Copyright for portions of the Source code contained in this file is owned
  either by Creative Solutions or David Sibley"


## Acknowledgements

Special thanks to:

- The classic Macintosh preservation community
- The people at Chipwits who have maintained copies of the original software
