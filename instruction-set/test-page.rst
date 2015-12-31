ASM Format
********************************

Every program in assembly follows a specific format.

.. code-block:: asm

 .nolist
 #include "includes\ti84pce.inc"
 .list
 .assume ADL=1
 .org userMem-2
 .db tExtTok,tAsm84CeCmp
 ;program code
 ret
 
But what does all of this code do?

.. code-block:: asm
 
 .nolist

This tells the assembler information it needs to know, it's not important for us to know what it does, just that it's needed in every program for it to compile.
 
 
.. code-block:: asm

 #include "includes\ti84pce.inc" 

This tells our compiler where everything is located inside the OS 


.. code-block:: asm

 .list
 .assume ADL=1
 .org userMem-2
 .db tExtTok,tAsm84CeCmp 

Read .nolist's description

This is where you would write the program's code



.. code-block:: asm
 
 ret 
 
This ends the program in most cases

*In the next tutorial, we'll be learning about how information is stored on your calculator.*
