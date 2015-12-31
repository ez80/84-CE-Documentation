Registers and Indirection
********************************

If you've ever programmed in a different language, you've used something called variables to store your data temporarily. In assembly, we use registers.

There are many registers you can use in assembly. The ones we will be covering today are: A, B, C, D, E, F, H, and L, which can be paired together to form AF, BC, DE, and HL. As you probably have guessed, when a register is paired with another it can hold more information.

Recall from the last tutorial bits and bytes? H is a 1 byte register, or 8 bits, while HL is a 2 byte register, or 16 bits. Now that we know about registers, it's time we learn our first instruction!

.. code-block:: asm
 
  ld destination,source 
  
What does this code do? It puts the value of source into the given destination.
We can use registers as arguments for this command: 

.. code-block:: asm
 
  ld hl,de 
  
Puts the content of DE inside HL.

We can also use numbers:

.. code-block:: asm
 
  ld hl,7

Puts 7 into HL.  

Remember the size of the registers you are using:

.. code-block:: asm
 
  ld hl,a

This is a valid instruction, it puts A into HL
  
.. code-block:: asm
 
  ld a,hl

This is not a valid instruction, HL is a 2 byte register and cannot fit into A, which is a 1 byte register. This means that the least significant byte will be ignored.
