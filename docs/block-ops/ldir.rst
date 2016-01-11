LDIR
--------

**The Legendary LDIR**
	Load And Increment with Style

**Description**
	| Performs ``ldi`` until ``BC`` = 0, effectively copying ``BC`` bytes of data from ``HL`` to ``DE``, where ``HL`` and ``DE`` point to the start of their respective blocks.

		.. code-block:: asm

			ldi
			ret po
			jr -5

**Uses**
	- Copying lots of data
		- Sprite routines
		- Copying graphical data from some buffer to the actual screen
		- Filling lots of space with one (or more) bytes

**Results**
	================    ==========================================  ========================================
	Register/Flag       16-bit (non-ADL)                            24-bit (ADL)
	================    ==========================================  ========================================
	``S`` flag          Not affected
	----------------    ------------------------------------------------------------------------------------
	``Z`` flag          Not affected
	----------------    ------------------------------------------------------------------------------------
	``H`` flag          Reset
	----------------    ------------------------------------------------------------------------------------
	``P/V`` flag        Set if ``BC`` ≠ 0 after the operation; else reset
	----------------    ------------------------------------------------------------------------------------
	``N`` flag          Reset
	----------------    ------------------------------------------------------------------------------------
	``C`` flag          Not affected
	================    ====================================================================================

**Allowed Instructions**
	================  ================  ==========================  ==========================  ==========================
	Instruction       Opcode            CC (ADL/non-ADL)            CC (.S)                     CC (.L)
	================  ================  ==========================  ==========================  ==========================
	ldir              $ED, $B0          2F + (1R + 1W + 1)* ``BC``  3F + (1R + 1W + 1)* ``BC``  3F + (1R + 1W + 1)* ``BC``
	================  ================  ==========================  ==========================  ==========================

**Notes**
	- Interrupts can be triggered while this instruction is in progress (unless they are disabled using ``DI``, of course).
	- Assuming you are copying hard-coded data and BC is NOT already set to the desired number of bytes, it is only faster to use hard-coded ``LDI`` s instead of ``ld bc,BytesToCopy \ ldir`` if you are copying two bytes. Copying three bytes, the cycle times and size of the code are exactly the same (6 bytes, 6F+3R+3W+3).
	- If you want to copy a few more bytes than whatever number is in ``BC``, it is both smaller and significantly faster to use ``INC BC`` several times before ``LDIR`` than a few ``LDI`` s after it. (``INC BC`` is one byte and only 1F (plus the extra 1R + 1W + 1 from ``LDIR``) whereas ``LDI`` is two bytes and 2F+1R+1W+1. So you just save one byte and 1F.)

**Examples**
	- Filling a block of memory with a single byte

			.. code-block:: asm

				ld hl,StartOfData
				ld de,StartOfData+1
				ld bc,SizeOfData-1
				ld (hl),ByteToCopy
				ldir

	- Copy graphical data from vBuf2 to vBuf1

			.. code-block:: asm

				ld hl,vBuf2
				ld de,vBuf1
				ld bc,320*240
				ldir

	- Set up a hard-coded 8bpp palette

			.. code-block:: asm

				ld hl,Palette_Start
				ld de,mpLcdPalette
				ld bc,Palette_End-Palette_Start
				ldir

	- A simple 8bpp rectangle drawing routine (credit: MateoConLechuga)

			.. code-block:: asm

				; INPUTS
				; BC				Width
				; DE				X-position
				; H					Height
				; L					Y-position
				; (FillRect_Color)	Color
				FillRect:
					ld a,h ; Store the height in A to be used as a loop counter
					ld h,160
					mlt hl
					add hl,hl ; HL now contains the Y position multiplied by 320
					add hl,de ; Add in the X position...
					ld de,vBuf1
					add hl,de ; And the LCD memory location...
					; Now HL is pointing to the first pixel of the rectangle
					dec bc ; Get the rectangle width minus 1 in BC (more on that later)
				FillRect_Loop:
				FillRect_Color = $+1
					ld (hl),0 ; This is self-modifying code
					push hl
					pop de
					inc de ; Now DE = HL + 1
					push bc ; Save BC for later
					ldir ; Copy BC (width-1) bytes from HL (first pixel of this row of the rectangle) to DE (next pixel)
					; Now one row of the rectangle is done
					pop bc ; Grab BC again
					ld de,320
					add hl,de ; Advanced HL one pixel down...
					sbc hl,bc ; And return to the left edge of the rectangle
					dec a ; Decrement our loop counter...
					jr nz,FillRect_Loop ; And repeat if we haven't finished
					ret

**See Also**
	`CPIR <cpir.html>`_, `LD </en/latest/docs/ld-ex/ld.html>`_, `LDD <ldd.html>`_, `LDDR <lddr.html>`_, `LDI <ldi.html>`_
