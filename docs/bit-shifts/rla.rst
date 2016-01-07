RLA
--------

**RLA**
	Rotate Left Accumulator

**Description**
	| Performs a very fast ``RL A``; the 7th bit of ``A`` is moved into the carry, and the carry is moved into the 0th bit of ``A``.
	.. image:: img/rl.png

**Uses**
	- Quickly multiplying ``A`` by two
	- Retrieving consecutive bits of a byte in a loop, starting from the left

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``A``               .. image:: img/small/rl.png
	``S`` flag          Not affected
	``Z`` flag          Not affected
	``H`` flag          Reset
	``P/V`` flag        Not affected
	``N`` flag          Reset
	``C`` flag          7th bit of ``M``
	================    ==============================================

**Allowed Instructions**
	================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)
	================  ================  ================
	rla               $17               1F              
	================  ================  ================

**Notes**
	- When using ``RLA`` to multiply ``A`` by 2, first make sure the carry flag is reset the result will be ``( A * 2 ) + Carry``.
	- Note that unlike ``RL A``, this instruction does not meaningfully affect any flags except ``C``.

**See Also**
	`RLA <rla.html>`_, `RLC <rlc.html>`_, `RR <rr.html>`_, `SLA <sla.html>`_

.. _`RL A`: rl.html
