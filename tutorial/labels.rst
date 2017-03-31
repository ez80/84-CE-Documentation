Labels
================================

Labels consist of an identifier (or symbol) followed by a colon (:). The identifier can contain numbers, letters, and ``_``, but cannot start with a number. Labels must be defined only once.

When a program is compiled, each label is replaced with a 24bit address. A label can be used to identify a string of data, a location to jump to, or a subroutine to call.

From the example program:

.. code-block:: asm

 .nolist
 #include "includes\ti84pce.inc"
 .list
 .assume ADL=1
 .org userMem-2
 .db tExtTok,tAsm84CeCmp
  call _homeup
  call _ClrScrnFull
  ld hl,TutorialText
  call _PutS
  call _GetKey
  call _ClrScrnFull
  res donePrgm,(iy+doneFlags)
  ret
 TutorialText:
  .db "Excellent job! :) You havecreated your first assembly program!",0
  
The label ``TutorialText`` is used by the compiler to store the location of the start of the string. (``TutorialText`` now refers to the 24bit address of the start of the string.)

.. code-block:: 

  ld hl,TutorialText
  call _PutS
  
Here, the value of the label ``TutorialText`` is loaded into hl (the address of the start of the string) and ``call _PutS`` displays the string located at the address in hl. ``_PutS`` itself is also a label (defined in ``ti84pce.inc``) that refers to the address of a subroutine built into TI-OS.
