RL
--------

**RL M**
	Rotate Left

**Description**
	| Performs a left shift on ``M``; the 7th bit of ``M`` is moved into the carry, and the carry is moved into the 0th bit of ``M``.
	.. image:: img/rl.png

**Uses**
	- Quickly multiplying by two
	- Retrieving consecutive bits of a byte in a loop, starting from the left

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``M``               .. image:: img/small/rl.png
	``S`` flag          Set if the result is negative; else reset
	``Z`` flag          Set if the result is 0; else reset
	``H`` flag          Reset
	``P/V`` flag        Set if the result has even parity_; else reset
	``N`` flag          Reset
	``C`` flag          7th bit of ``M``
	================    ==============================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	rl a              $CB, $17          2F                X                 X
	rl b              $CB, $10          2F                X                 X
	rl c              $CB, $11          2F                X                 X
	rl d              $CB, $12          2F                X                 X
	rl e              $CB, $13          2F                X                 X
	rl h              $CB, $14          2F                X                 X
	rl l              $CB, $15          2F                X                 X
	rl (hl)           $CB, $16          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	rl (ix+n)         $DD, $CB, n, $16  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	rl (iy+n)         $FD, $CB, n, $16  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- When using ``RL`` to multiply a number by 2, first make sure the carry flag is reset or the result will be ``( M * 2 ) + Carry``.

**See Also**
	`RLA <rla.html>`_, `RLC <rlc.html>`_, `RR <rr.html>`_, `SLA <sla.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
