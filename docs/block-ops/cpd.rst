CPD
--------

**CPD**
	Compare and Decrement

**Description**
	| Performs ``cp a,(hl)``, then decrements HL and BC.
	.. codeblock:: asm
		cp a,(hl)
		dec hl
		dec bc

**Uses**
	- This instruction is not very useful on its own, as ``cp a,(hl)`` is both smaller and faster than a single ``CPD``, but more often used is the repeating version of ``CPD``: ``CPDR``

**Results**
	================    ==========================================  ========================================
	Register/Flag       16-bit (non-ADL)                            24-bit (ADL)
	================    ==========================================  ========================================
	``S`` flag          Set if result is negative; else reset
	----------------    ------------------------------------------------------------------------------------
	``Z`` flag          Set if ``A`` = ``(HL)``; else reset
	----------------    ------------------------------------------------------------------------------------
	``H`` flag          Set if borrow from bit 4; else reset
	----------------    ------------------------------------------------------------------------------------
	``P/V`` flag        Set if ``BC`` ≠ 0 after the operation; else reset
	----------------    ------------------------------------------------------------------------------------
	``N`` flag          Set
	----------------    ------------------------------------------------------------------------------------
	``C`` flag          Not affected
	================    ====================================================================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	cpd               $ED, $A9          2F + 1R           3F + 1R           3F + 1R
	================  ================  ================  ================  ================

**See Also**
	`CP </en/latest/arithmetic/cp.html>`_, `CPDR <cpdr.html>`_, `CPI <cpi.html>`_, `CPIR <cpir.html>`_, `LDD <ldd.html>`_
