LDDR
--------

**LDDR**
	Compare and Decrement with Repeat

**Description**
	| Performs ``ldd`` until ``BC`` = 0, effectively copying ``BC`` bytes of data from ``HL`` to ``DE``, where ``HL`` and ``DE`` point to the end of their respective blocks.

		.. code-block:: asm

			ldd
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
	lddr              $ED, $B8          2F + (1R + 1W + 1)*``BC``  3F + (1R + 1W + 1)*``BC``  3F + (1R + 1W + 1)*``BC``
	================  ================  =========================  =========================  =========================

**Notes**
	- Interrupts can be triggered while this instruction is in progress (unless they are disabled using ``DI``, of course).
	- Since most of the time it's more convenient to specify the beginning of a block of data than the end, ``LDIR`` is significantly more popular than ``LDDR``.
	- Assuming you are copying hard-coded data and BC is NOT already set to the desired number of bytes, it is only faster to use hard-coded ``LDD``s instead of ``ld bc,BytesToCopy \ lddr`` if you are copying two bytes. Copying three bytes, the cycle times and size of the code are exactly the same (6 bytes, 6F+3R+3W+3).
	- If you want to copy a few more bytes than whatever number is in ``BC``, it is both smaller and significantly faster to use ``INC BC`` several times than ``LDD``. (``INC BC`` is one byte and only 1F whereas ``LDD`` is two bytes and 2F+1R+1W+1.)

**Examples**
	.. code-block:: asm

		; Filling a block of memory with a single byte
			ld hl,EndOfBlock
			ld de,EndOfBlock-1
			ld bc,SizeOfBlock-1
			ld (hl),ByteToCopy
			lddr

**See Also**
	`CPDR <cpdr.html>`_, `LD </en/latest/docs/ld-ex/ld.html>`_, `LDD <ldd.html>`_, `LDI <ldi.html>`_, `LDIR <ldir.html>`_
