Labels
================================

Labels consist of an identifier (or symbol) followed by a colon (:). Labels must be defined only once.

When compiled, a label is compiled into a 24bit address. A label can be used to store a string of data, a location to jump to, or a subroutine to call.

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
  
The label ``TutorialText`` is used to store the location of the string. Meaning: the address of the start of the string is stored in ``TutorialText``.

.. code-block:: 

  ld hl,TutorialText
  call _PutS
  
Here, the label ``TutorialText`` is loaded into hl (the address of the start of the string) and ```call _PutS``` displays the string located at the address in hl.
