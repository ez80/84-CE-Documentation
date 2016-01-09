LDIR
--------

**The Legendary LDIR**
	Load And Increment with Style

**Description**
	| Performs ``ldi`` until ``BC`` = 0, effectively copying ``BC`` bytes of data from ``HL`` to ``DE``, where ``HL`` and ``DE`` point to the start of their respective blocks.
	.. codeblock:: asm

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
	================  ================  =========================  =========================  =========================
	Instruction       Opcode            CC (ADL/non-ADL)           CC (.S)                    CC (.L)
	================  ================  =========================  =========================  =========================
	ldir              $ED, $B0          2F + (1R + 1W + 1)*``BC``  3F + (1R + 1W + 1)*``BC``  3F + (1R + 1W + 1)*``BC``
	================  ================  =========================  =========================  =========================

**Notes**
	- Interrupts can be triggered while this instruction is in progress (unless they are disabled using ``DI``, of course).
	- Assuming you are copying hard-coded data and BC is NOT already set to the desired number of bytes, it is only faster to use hard-coded ``LDI``s instead of ``ld bc,BytesToCopy \ ldir`` if you are copying two bytes. Copying three bytes, the cycle times and size of the code are exactly the same (6 bytes, 6F+3R+3W+3).
	- If you want to copy a few more bytes than whatever number is in ``BC``, it is both smaller and significantly faster to use ``INC BC`` several times before ``LDIR`` than a few ``LDI``s after it. (``INC BC`` is one byte and only 1F whereas ``LDI`` is two bytes and 2F+1R+1W+1.)

**Examples**

	.. codeblock:: asm

		; Filling a block of memory with a single byte
			ld hl,StartOfBlock
			ld de,StartOfBlock+1
			ld bc,SizeOfBlock-1
			ld (hl),ByteToCopy
			ldir

**See Also**
	`CPIR <cpir.html>`_, `LD </en/latest/docs/ld-ex/ld.html>`_, `LDD <ldd.html>`_, `LDDR <lddr.html>`_, `LDI <ldi.html>`_
