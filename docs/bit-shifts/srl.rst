SRL
--------

**SRL M**
	Shift Right Logical

**Description**
	| Performs a right shift on ``M``; the 0th bit of ``M`` is moved into the carry, and a zero is placed in the 7th bit of ``M``.
	.. image:: img/srl.png

**Uses**
	- Quickly dividing a number by two

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``M``               .. image:: img/small/srl.png
	``S`` flag          Set if the result is negative; else reset
	``Z`` flag          Set if the result is 0; else reset
	``H`` flag          Reset
	``P/V`` flag        Set if the result has even parity_; else reset
	``N`` flag          Reset
	``C`` flag          0th bit of ``M``
	================    ==============================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	srl a             $CB, $3F          2F                X                 X
	srl b             $CB, $38          2F                X                 X
	srl c             $CB, $39          2F                X                 X
	srl d             $CB, $3A          2F                X                 X
	srl e             $CB, $3B          2F                X                 X
	srl h             $CB, $3C          2F                X                 X
	srl l             $CB, $3D          2F                X                 X
	srl (hl)          $CB, $3E          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	srl (ix+n)        $DD, $CB, n, $3E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	srl (iy+n)        $FD, $CB, n, $3E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- Unlike ``RR``, the initial state of the carry flag has no effect on the result of this instruction, so a number can be easily halved without worrying about the state of the carry flag.
	- Despite the mnemonics, the reverse of ``SRL`` is actually ``SLA`` (Shift Left Arithmetic).

**See Also**
	`RL <rl.html>`_, `RLC <rlc.html>`_, `SRA <sra.html>`_, `SRL <srl.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
