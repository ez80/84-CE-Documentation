Romcalls
================================

Romcalls are pieces of code that run system predefined functions.

A list of romcalls can be found `here <https://education.ti.com/~/media/01E6AF2CADF84171B6F2E2039357BAAC>`_, with one problem. 
Since this list is for the TI-83 Plus, some of the romcalls are missing or outdated. Also, the romcalls on the +CE are prefixed with a single underscore.

How does the assembler know where the romcalls on the TI-84+CE are? Surely they must be in a different location then the CE? The answer lies in the .inc file that you include at the start of every program.

.. code-block:: asm

 #include "includes\ti84pce.inc" 
 
Inside is a list of addresses that define where the romcalls (and other important items) are located. Each calculator has a different .inc file.

So how do we call a romcall?

.. code-block:: asm
  call _PutS
  
This will call the romcall _PutS, which as you can see in the system routines pdf, reads the string inside the address in HL.

Recall from the very first tutorial the example program

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

Now that we know romcalls, we can figure out what each line does.

.. code-block:: asm
  call _homeup
  call _ClrScrnFull

_HomeUp isn't in the System Routines file, but it and _ClrScrnFull set up for the text output by resetting the screen.


.. code-block:: asm
   ld hl,TutorialText
   call _PutS

From the last tutorial, we learned about labels, and how they are converted to addresses at runtime. Since _PutS reads from HL as an address, we can just put the address number, and not the contents inside HL. This means we do not use indirection and we do not need parenthesis.

_PutS reads a null terminating string from HL. All that means is that the string ends in 0.

.. code-block:: asm
  call _GetKey
  call _ClrScrnFull
  res donePrgm,(iy+doneFlags)
  ret
  
We call _GetKey to pause the program until a key is pressed.  Afterword, we clear the screen again using _ClrScrnFull.
Don't worry about the second to last line for now, we'll learn what it does later. Finally, the program ends.

Once again, you can learn more about each romcall in the PDF above. From now on, if there is a romcall you don't recognize, use the PDF.

*The next tutorial's contents are unknown*