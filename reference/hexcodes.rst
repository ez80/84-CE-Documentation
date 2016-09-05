Hexcodes
==========================

What are hex codes?
--------------------

Hex codes are little assembly programs that TI-BASIC programmers can use to add functionality to their programs. Here is an example of how to use a hexcode.

.. code-block:: asm

 Asm84CEPrgm
 3A8705D0CD080B02CD300F02C9

Each hex code will have the program and the source in assembly, along with a brief description of the functionality.

**Make sure you have the FULL, correct hexcode. These programs can clear your ram if not entered correctly!**

General
--------------------
Toggle Program Mode
__________________________
When used in a program, it allows you to use Archive and UnArchive on other programs. Make sure to switch back to "program mode" when you're done by running the program again.
When used on the home screen, it allows you to use programming commands like If and For(; this has limited utility, but maybe it's useful to check a short bit of code without creating a new program for it.

.. code-block:: asm

 FD7E08EE02FD7708C9

.. code-block:: asm

  ld a,(iy+8)
  xor 2 
  ld (iy+8),a
  ret
 
Quick Key
__________________________
This is a getKey routine that makes all keys repeat, not just arrows and there is no delay between repeats. The key codes are different, so you might need to experiment.

.. code-block:: asm

 3A8705D0CD080B02CD300F02C9

.. code-block:: asm

  ld a,(kbdScanCode)
  call _SetXXOP1
  call _StoAns
  ret
 
 
Text Inverse
__________________________
This will switch from normal text mode to inverse (white text on black background) and vice versa.

.. code-block:: asm

 FD7E05EE08FD7705C9

.. code-block:: asm

  ld a,(iy+textFlags)
  xor 1&lt;&lt;textInverse
  ld (iy+textFlags),a
  ret

LCD
--------------------

LCD Clear
__________________________
This only clears the LCD, it doesn't actually clear the graph screen or homescreen

.. code-block:: asm

 CD080802C9

.. code-block:: asm

 call _ClrLCDFull
 ret
 
Fill Color
__________________________
This fills the LCD with pixels of the color you specify. Replace XX with the palettized color, list of available colors here: http://ce-programming.github.io/documentation/images/tutorials/asm/rgbhlpalette.png.

.. code-block:: asm

 3EXX210000D401005802CDE01002C9

.. code-block:: asm

 ld a,$XX
 ld hl,vRam
 ld bc,320*240*2
 call _MemSet
 ret
 
Black
__________________________
This fills the LCD with black pixels

.. code-block:: asm

 3E00210000D401005802CDE01002C9

.. code-block:: asm

 ld a,$00
 ld hl,vRam
 ld bc,320*240*2
 call _MemSet
 ret

White
__________________________
This fills the LCD with white pixels

.. code-block:: asm

 3EFF210000D401005802CDE01002C9

.. code-block:: asm

 ld a,$FF
 ld hl,vRam
 ld bc,320*240*2
 call _MemSet
 ret
 
Run Indicator
--------------------
On
__________________________
This turns on the run indicator.

.. code-block:: asm

 CD440802C9

.. code-block:: asm

 call _RunIndicOn
 ret 
 
Off
__________________________
This turns off the run indicator.

.. code-block:: asm

 CD480802C9

.. code-block:: asm

 call _RunIndicOff
 ret
 
Hexcode descriptions originally from `TI-BD <http://tibasicdev.wikidot.com/hexcodes>`_. 
