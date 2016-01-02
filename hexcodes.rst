Hexcodes
================================

What are hex codes?
--------------------

Hex codes are little assembly programs that TI-BASIC programmers can use to add functionality to their programs. Here is an example of how to use a hexcode.

.. code-block:: asm

Asm84CEPrgm
3A8705D0CD080B02CD300F02C9

Each hex code will have the program and the source in assembly, along with a brief description of the functionality.

**Make sure you have the FULL, correct hexcode. These programs can clear your ram if not entered correctly!**

Toggle Program Mode
____________________

When used in a program, it allows you to use Archive and UnArchive on other programs. Make sure to switch back to "program mode" when you're done by running the program again.
:rawhtml:`<br>`_
When used on the home screen, it allows you to use programming commands like If and For(; this has limited utility, but maybe it's useful to check a short bit of code without creating a new program for it.

``FD7E08EE02FD7708C9``

.. code-block:: asm

 ld a,(iy+8)
 xor 2 
 ld (iy+8),a
 ret