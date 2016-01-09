LDD
--------

**LDD**
	Load and Decrement

**Description**
	| Copies one byte from ``(HL)`` to ``(DE)``, then decrements ``HL``, ``DE``, and ``BC``.

		.. code-block:: asm

			ld (de),(hl) ; Not normally a valid instruction
			dec hl
			dec de
			dec bc

**Uses**
	- This instruction is not very useful on its own, but is more often used is the repeating version of ``LDD``: ``LDDR``

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
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	ldi               $ED, $A8          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- If all you want to accomplish is ``ld (de),(hl)``, consider ``ld a,(hl) \ ld (de),a``. It is the same size but is one clock cycle less and doesn't modify any of the registers except ``A``.

**See Also**
	`CPD <cpd.html>`_, `LD </en/latest/docs/ld-ex/ld.html>`_, `LDI <ldi.html>`_, `LDDR <lddr.html>`_, `LDIR <ldir.html>`_
