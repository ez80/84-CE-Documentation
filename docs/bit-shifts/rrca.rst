RRCA
--------

**RRCA**
	Rotate Right Circular Accumulator

**Description**
	| Performs a very fast ``RRC A``; the 0th bit of ``A`` is copied into the carry and into the 7th bit of ``A``.
	.. image:: img/rrc.png

**Uses**
	- Retrieving consecutive bits of a byte in a loop, starting from the right, without affecting the source data (after eight iterations)

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``A``               .. image:: img/small/rr.png
	``S`` flag          Not affected
	``Z`` flag          Not affected
	``H`` flag          Reset
	``P/V`` flag        Not affected
	``N`` flag          Reset
	``C`` flag          0th bit of ``A``
	================    ==============================================

**Allowed Instructions**
	================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)
	================  ================  ================
	rra               $0F               1F              
	================  ================  ================

**Notes**
	- Unlike ``RR``, the initial state of the carry flag has no effect on the result of this instruction.
	- Unlike ``RRC A``, this instruction does not meaningfully affect any flags except ``C``.

**See Also**
	`RLCA <rlca.html>`_, `RRA <rra.html>`_, `RRC <rrc.html>`_
