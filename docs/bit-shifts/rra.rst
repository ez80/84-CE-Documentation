RRA
--------

**RRA**
	Rotate Right Accumulator

**Description**
	| Performs a very fast ``RR A``_; the 0th bit of ``A`` is moved into the carry, and the carry is moved into the 7th bit of ``A``.
	.. image:: img/rr.png

**Uses**
	- Quickly dividing ``A`` by two (carry flag is set if there was a remainder)
	- Retrieving consecutive bits of a byte in a loop, starting from the left

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
	``C`` flag          0th bit of ``M``
	================    ==============================================

**Allowed Instructions**
	================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)
	================  ================  ================
	rra               $1F               1F              
	================  ================  ================

**Notes**
	- When using ``RRA`` to divide ``A`` by 2, first make sure the carry flag is reset or the result will be ``( A * 2 ) + ( 128 * Carry )``.
	- Note that unlike ``RR A``, this instruction does not meaningfully affect any flags except ``C``.

**See Also**
	`RLA <rla.html>`_, `RR <rr.html>`_, `RRCA <rrca.html>`_

.. _`RR A`: rl.html
