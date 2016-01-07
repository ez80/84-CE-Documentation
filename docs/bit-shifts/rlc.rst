RLC
--------

**RLC M**
	Rotate Left Circular

**Description**
	| Performs a left shift on ``M``; the 7th bit of ``M`` is copied into the carry and into the 0th bit of ``M``.
	.. image:: img/rlc.png

**Uses**
	- Retrieving consecutive bits of a byte in a loop, starting from the left, without affecting the source data (after eight iterations

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``M``               .. image:: img/small/rlc.png
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
	rlc a             $CB, $07          2F                X                 X
	rlc b             $CB, $00          2F                X                 X
	rlc c             $CB, $01          2F                X                 X
	rlc d             $CB, $02          2F                X                 X
	rlc e             $CB, $03          2F                X                 X
	rlc h             $CB, $04          2F                X                 X
	rlc l             $CB, $05          2F                X                 X
	rlc (hl)          $CB, $06          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	rlc (ix+n)        $DD, $CB, n, $06  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	rlc (iy+n)        $FD, $CB, n, $06  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- Unlike ``RL``, the initial state of the carry flag has no effect on the result of this instruction.

**See Also**
	`RL <rl.html>`_, `RLCA <rlca.html>`_, `RRC <rrc.html>`_, `SLA <sla.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
