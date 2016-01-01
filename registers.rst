Registers and Indirection
********************************

The Registers
______________

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

Addresses
______________

To fully understand what indirection is, we have to know what an address is. An address is a number that corresponds to a specific byte in RAM.
Add one to the address and you go forward a byte; subtract one and you go backward a byte.

You can use addresses in place of registers with the LD instruction

.. code-block:: asm
 
  ld hl,(133212)
  
This will put whatever is inside address 133212, the 133213th byte, and the 2 bytes after that (hl is 3 bytes), inside the hl register pair.

But why do we have parenthesis around the address? This is something called indirection.

Indirection
______________

*Note: Indirection is slightly hard to grasp for newcomers, and we'll touch more on this later, so just do your best*

Indirection tells you whether or not you are using the number as an address, or just as a number. Here the example from above:

.. code-block:: asm
 
  ld hl,(133212)

How does the program know whether you are talking about the 133213th byte or the actual number 133212? The parenthesis tell the program to use the number as an address.

.. code-block:: asm

  ld hl,133212 ;let's put 133212 inside hl. Note, there are no parenthesis, so we're talking about the number 133212, and not the 133213th byte.
  ld a,2 ;also no parenthesis, we mean 2
  ld (hl),a ;we can decide later to use it as an address, by putting the parenthesis around it. Now we are putting the value of A, 2, inside the address stored in hl.
  
Don't worry if you don't immediately get it, it will come to you eventually. Now it's your turn to try

.. code-block:: asm

  ld de,(133215)
  ld (132918),de
  
If you know what's happening here, good for you! If you don't, it's ok. You'll get it later.

*In the next tutorial, we'll learn about...?*
  