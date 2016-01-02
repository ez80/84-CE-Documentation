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
--------------------

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
--------------------

This is a getKey routine that makes all keys repeat, not just arrows and there is no delay between repeats. The key codes are different, so you might need to experiment.

.. code-block:: asm

 3A8705D0CD080B02CD300F02C9

.. code-block:: asm

  ld a,(kbdScanCode)
  call _SetXXOP1
  call _StoAns
  ret
 
 
Text Inverse
--------------------

This will switch from normal text mode to inverse (white text on black background) and vice versa.

.. code-block:: asm

 FD7E05EE08FD7705C9

.. code-block:: asm

  ld a,(iy+textFlags)
  xor 1&lt;&lt;textInverse
  ld (iy+textFlags),a
  ret
 
Hexcode descriptions originally from `TI-BD <http://tibasicdev.wikidot.com/hexcodes>`_. 