RRC
--------

**RRC M**
	Rotate Right Circular

**Description**
	| Performs a right shift on ``M``; the 0th bit of ``M`` is copied into the carry and into the 7th bit of ``M``.
	.. image:: img/rr.png

**Uses**
	- Retrieving consecutive bits of a byte in a loop, starting from the right, without affecting the source data (after eight iterations)

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``M``               .. image:: img/small/rrc.png
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
	rr a              $CB, $0F          2F                X                 X
	rr b              $CB, $08          2F                X                 X
	rr c              $CB, $09          2F                X                 X
	rr d              $CB, $0A          2F                X                 X
	rr e              $CB, $0B          2F                X                 X
	rr h              $CB, $0C          2F                X                 X
	rr l              $CB, $0D          2F                X                 X
	rr (hl)           $CB, $0E          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	rr (ix+n)         $DD, $CB, n, $0E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	rr (iy+n)         $FD, $CB, n, $0E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- Unlike ``RR``, the initial state of the carry flag has no effect on the result of this instruction.

**See Also**
	`RLC <rr.html>`_, `RR <rra.html>`_, `RRCA <rrc.html>`_, `SRA <sra.html>`_, `SRL <srl.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
