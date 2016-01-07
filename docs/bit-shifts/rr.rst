RR
--------

**RR M**
	Rotate Right

**Description**
	| Performs a right shift on ``M``; the 0th bit of ``M`` is moved into the carry, and the carry is moved into the 7th bit of ``M``.
	.. image:: /en/latest/images/rr.png

**Uses**
	- Quickly dividing by two (carry flag is set if there was a remainder)
	- Retrieving consecutive bits of a byte in a loop, starting from the left

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``M``               .. image:: /en/latest/images/small/rr.png
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
	rr a              $CB, $1F          2F                X                 X
	rr b              $CB, $18          2F                X                 X
	rr c              $CB, $19          2F                X                 X
	rr d              $CB, $1A          2F                X                 X
	rr e              $CB, $1B          2F                X                 X
	rr h              $CB, $1C          2F                X                 X
	rr l              $CB, $1D          2F                X                 X
	rr (hl)           $CB, $1E          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	rr (ix+n)         $DD, $CB, n, $1E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	rr (iy+n)         $FD, $CB, n, $1E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- When using ``RR`` to divide a number by 2, first make sure the carry flag is reset or the result will be ``( M * 2 ) + ( 128 * Carry )``.

**See Also**
	`RL <rr.html>`_, `RRA <rra.html>`_, `RRC <rrc.html>`_, `SRA <sra.html>`_, `SRL <srl.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
