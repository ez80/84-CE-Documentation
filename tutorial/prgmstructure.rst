Program Structure
********************************

Every program in assembly follows a specific format.

.. code-block:: asm

 #include "includes\ti84pce.inc"
 .assume ADL=1
 .org userMem-2
  .db tExtTok,tAsm84CeCmp

  ; Program code

  ret

But what does all of this code do?

.. code-block:: asm

 #include "includes\ti84pce.inc"

This is a file that includes lots of locations of routines and variables and various other things in the calculator's operating system that we can use.


.. code-block:: asm

 .assume ADL=1

This tells the assembler to assume that ADL mode is on. ADL mode means the processor is using 24-bit register pairs and memory addresses, which is the the calculator's default.


.. code-block:: asm

 .org userMem-2

This tells the assembler that this program will be located at ``userMem-2``, so any memory addresses we reference should be relative to that. (The program is actually placed at ``userMem``, but there are two bytes right after this which are removed from the program by the OS before it is placed at ``userMem``.)


.. code-block:: asm

  .db tExtTok,tAsm84CeCmp

This is exactly equivalent to the ``Asm84CEPrgm`` token in BASIC; it tells your calculator that it should be executing an assembly program instead of a BASIC program. This is why when you try to run an assembly program on your calculator without the ``Asm(`` token, you get an error (and why you can't run a BASIC program with the ``Asm(`` token).


.. code-block:: asm

  ; Program code

This is where you can actually write the program's code.


.. code-block:: asm

  ret

This exits the program (usually). More on that later.

*In the next tutorial we'll be learn about how numbers work on your calculator.*
