Registers and Indirection
********************************

If you've ever programmed in a different language, you've used something called variables to store your data temporarily. In assembly, we use registers.

There are many registers you can use in assembly. The ones we will be covering today are: A, B, C, D, E, F, H, and L, which can be paired together to form AF, BC, DE, and HL. As you probably have guessed, when a register is paired with another it can hold more information.

Recall from the last tutorial bits and bytes? H is a 1 byte register, or 8 bits, while HL is a 3 byte register pair, or 24 bits. 

Now that we know about registers, it's time we learn our first instruction!

.. code-block:: asm
 
  ld destination,source 
  
What does this code do? It puts the value of source into the given destination.
We can use registers as arguments for this instruction: 

.. code-block:: asm
 
  ld h,d
  
Puts the content of D inside H.


We can also use numbers:

.. code-block:: asm
 
  ld hl,7

Puts 7 into HL.  


Remember the size of the registers you are using:

.. code-block:: asm
 
  ld hl,a

This not a valid instruction, as both arguments have to be 8 bit registers.