Introduction to Assembly
********************************
You want more games for your shiny new TI-84+CE? Why don't you make them yourself?

What is assembly?
=================================================
Assembly is a very powerful language that you can use on your TI-84+CE! When you write in assembly, you write in a human readable form of machine code, which allows you to create quicker programs that can access and do more than TI-BASIC.
Mistakes in assembly can be messier than in TI-BASIC- but usually only as severe as a ram clear, so before you start this guide, back up your calculator to prevent any data loss!

Setting up
=================================================

What you'll need
--------------------------------------------------

A program editor
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
To write your program, you can use almost any text editor. We prefer Notepad++, as it is really easy to use for beginners and it has some nice features for developing.

| Download Here: `Notepad++ <https://notepad-plus-plus.org/download/>`_
| Syntax Highlighting: `Notepad++ eZ80 Syntax Highlighting <http://cemete.ch/p243171>`_

An assembler
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
An assembler lets you take the code you have created and make it into a program that the TI-84 Plus CE can use. We recommend SPASM-ng when coding in eZ80.

Download Here: `Spasm-ng <https://github.com/alberthdev/spasm-ng/releases>`_

A debugger/emulator or a TI-84+CE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
A debugger is useful for seeing what your code does and finding errors. Unfortunately, at the time of this writing, the only 84+CE emulator available for download is CEmu, which is hardly in a usable state. Because of this, we need TI's Connect software to transfer our programs to our calculator, and we'll also need a link cable (which should have come with your calculator) and the calculator itself.

Download Here: `TI Connect CE <https://education.ti.com/en/us/software/details/en/CA9C74CAD02440A69FDC7189D7E1B6C2/swticonnectcesoftware>`_

TI 84+CE Equates File
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
This file tells your program and the compiler where things are located on your calculator.

Download Here: `ti84pce.inc <http://wikiti.brandonw.net/index.php?title=84PCE:OS:Include_File>`_

Setting up the assembler
--------------------------------------------------
Alright, now we can get to putting together all the materials we just downloaded!
Create a folder and call it "My First ASM Program" (or anything else). Inside create three folders: ``bin``, ``includes``, and ``tools``. Rename ``SPASM`` to just ``spasm.exe`` and put it inside the folder named tools. Put ti84pce.inc inside the includes folder.

Create a file named ``Example.asm`` in your folder. Inside this file, write the following code.

.. code-block:: asm
 
 #include "includes\ti84pce.inc"
 
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

*Don't worry; we'll revisit what all this code does later on.*

Now, create a file named ``build.bat``. Inside this file, write the following code:

.. code-block:: shell

 @echo off
 :A
 tools\spasm -E -T Example.asm bin\Example.8xp
 Pause
 Goto A

Run ``build.bat`` by double-clicking on it. Inside the "bin" folder you should see a file named FIRSTPRGM.8xp. Transfer this onto your calculator using TI Connect CE and run it by pressing ``2nd`` → ``Catalog`` and selecting the ``Asm(`` token, then pressing ``Prgm`` and selecting ``EXAMPLE`` (or whatever you program was called). It should look something like this: ``Asm(prgmEXAMPLE``

If this doesn't work, try again to make sure you followed each step of the tutorial again. You can also post for help on the `Cemetech forums <http://cemetech.net/>`_.

*In the next lesson we'll dive right into learning assembly.*
