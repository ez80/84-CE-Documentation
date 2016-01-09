CPI
--------

**CPI**
	Compare and Increment

**Description**
	| Performs ``cp a,(hl)``, then increments ``HL`` and decrements ``BC``.
	.. code-block:: asm
		cp a,(hl)
		inc hl
		dec bc

**Uses**
	- This instruction is not very useful on its own, as ``cp a,(hl)`` is both smaller and faster than a single ``CPI``, but is more often used is the repeating version of ``CPI``: ``CPIR``

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
	cpi               $ED, $A1          2F + 1R           3F + 1R           3F + 1R
	================  ================  ================  ================  ================

**Notes**
	- Although this instruction increments ``HL``, it decrements ``BC``.

**See Also**
	`CP </en/latest/docs/arithmetic/cp.html>`_, `CPD <cpd.html>`_, `CPDR <cpdr.html>`_, `CPIR <cpir.html>`_, `LDI <ldi.html>`_
