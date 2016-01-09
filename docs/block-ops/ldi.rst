LDI
--------

**LDI**
	Load and Increment

**Description**
	| Copies one byte from ``(HL)`` to ``(DE)``, then increments ``HL``, increments ``DE``, and decrements ``BC``.

.. code-block:: asm

	ld (de),(hl) ; Not normally a valid instruction
	inc hl
	inc de
	dec bc

**Uses**
	- This instruction is not very useful on its own, but is more often used is the repeating version of ``LDI``: ``LDIR``

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
	ldi               $ED, $A0          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- Although this instruction increments ``HL`` and ``DE``, it decrements ``BC``.
	- If all you want to accomplish is ``ld (de),(hl)``, consider ``ld a,(hl) \ ld (de),a``. It is the same size but is one clock cycle less and doesn't modify any of the registers except ``A``.

**See Also**
	`CPI <cpi.html>`_, `LD </en/latest/docs/ld-ex/ld.html>`_, `LDD <ldd.html>`_, `LDDR <lddr.html>`_, `LDIR <ldir.html>`_
