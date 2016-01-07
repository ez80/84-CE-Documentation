RLCA
--------

**RLCA**
	Rotate Left Circular Accumulator

**Description**
	| Performs a very fast ``RLC A``; the 7th bit of ``A`` is copied into the carry and into the 0th bit of ``A``.
	.. image:: img/rlc.png

**Uses**
	- Retrieving consecutive bits of a byte in a loop, starting from the left, without affecting the source data (after eight iterations)

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``A``               .. image:: img/small/rlc.png
	``S`` flag          Not affected
	``Z`` flag          Not affected
	``H`` flag          Reset
	``P/V`` flag        Not affected
	``N`` flag          Reset
	``C`` flag          7th bit of ``A``
	================    ==============================================

**Allowed Instructions**
	================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)
	================  ================  ================
	rlca              $07               1F              
	================  ================  ================

**Notes**
	- Unlike ``RL``, the initial state of the carry flag has no effect on the result of this instruction.
	- Unlike ``RLC A``, this instruction does not meaningfully affect any flags except ``C``.

**See Also**
	`RLA <rla.html>`_, `RLC <rlc.html>`_, `RRCA <rrca.html>`_
