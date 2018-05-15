8x8 monochrome bitmap font for rendering
=========================================

A collection of header files containing a 8x8 bitmap font.

font8x8.h contains all available characters
font8x8_basic.h contains unicode points U+0000 - U+007F
font8x8_latin.h contains unicode points U+0000 - U+00FF

Author: Daniel Hepper <daniel@hepper.net>
License: Public Domain

Encoding
========
Every character in the font is encoded row-wise in 8 bytes.

The least significant bit of each byte corresponds to the first pixel in a
 row. 

The character 'A' (0x41 / 65) is encoded as 
{ 0x0C, 0x1E, 0x33, 0x33, 0x3F, 0x33, 0x33, 0x00}


    0x0C => 0000 1100 => ..XX....
    0X1E => 0001 1110 => .XXXX...
    0x33 => 0011 0011 => XX..XX..
    0x33 => 0011 0011 => XX..XX..
    0x3F => 0011 1111 => xxxxxx..
    0x33 => 0011 0011 => XX..XX..
    0x33 => 0011 0011 => XX..XX..
    0x00 => 0000 0000 => ........

To access the nth pixel in a row, right-shift by n.

                         . . X X . . . .
                         | | | | | | | |
    (0x0C >> 0) & 1 == 0-+ | | | | | | |
    (0x0C >> 1) & 1 == 0---+ | | | | | |
    (0x0C >> 2) & 1 == 1-----+ | | | | |
    (0x0C >> 3) & 1 == 1-------+ | | | |
    (0x0C >> 4) & 1 == 0---------+ | | |
    (0x0C >> 5) & 1 == 0-----------+ | |
    (0x0C >> 6) & 1 == 0-------------+ |
    (0x0C >> 7) & 1 == 0---------------+


Renderer
========
To visualize the font, a simple renderer is included in render.c

    $ gcc render.c -o render
    $ ./render 65
      XX    
     XXXX   
    XX  XX  
    XX  XX  
    XXXXXX  
    XX  XX  
    XX  XX

Credits
=======
These header files are directly derived from an assembler file fetched from:
http://dimensionalrift.homelinux.net/combuster/mos3/?p=viewsource&file=/modules/gfx/font8_8.asm

Original header:

; Summary: font8_8.asm
; 8x8 monochrome bitmap fonts for rendering
;
; Author:
;     Marcel Sondaar
;     International Business Machines (public domain VGA fonts)
;
; License:
;     Public Domain
;


