SRA
--------

**SRA M**
	Shift Right Arithmetic

**Description**
	| Performs a right shift on ``M``; the 7th bit of ``M`` remains unchanged, and the 0th bit of ``M`` is moved into the carry.
	.. image:: img/sra.png

**Uses**
	- Quickly dividing a signed integer by two

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``M``               .. image:: img/small/sra.png
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
	sra a             $CB, $2F          2F                X                 X
	sra b             $CB, $28          2F                X                 X
	sra c             $CB, $29          2F                X                 X
	sra d             $CB, $2A          2F                X                 X
	sra e             $CB, $2B          2F                X                 X
	sra h             $CB, $2C          2F                X                 X
	sra l             $CB, $2D          2F                X                 X
	sra (hl)          $CB, $2E          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	sra (ix+n)        $DD, $CB, n, $2E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	sra (iy+n)        $FD, $CB, n, $2E  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- Unlike ``RR``, the initial state of the carry flag has no effect on the result of this instruction, so a signed number can be easily halved without worrying about the state of the carry flag.
	- Despite the mnemonics, ``SRA`` is not very similar to ``SLA`` (Shift Left Arithmetic), which is meant for unsigned integers. For a right-shifting version of ``SLA``, use ``SRL`` (Shift Right Logical).

**See Also**
	`RR <rl.html>`_, `RRC <rlc.html>`_, `SLA <sra.html>`_, `SRL <srl.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
