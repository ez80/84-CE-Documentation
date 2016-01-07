SLA
--------

**SLA M**
	Shift Left Arithmetic

**Description**
	| Performs a left shift on ``M``; the 7th bit of ``M`` is moved into the carry, and a zero is placed in the 0th bit of ``M``.
	.. image:: img/sla.png

**Uses**
	- Quickly multiplying by two

**Results**
	================    ==============================================
	Register/Flag       8-bit                                     
	================    ==============================================
	``M``               .. image:: img/small/sla.png
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
	sla a             $CB, $27          2F                X                 X
	sla b             $CB, $20          2F                X                 X
	sla c             $CB, $21          2F                X                 X
	sla d             $CB, $22          2F                X                 X
	sla e             $CB, $23          2F                X                 X
	sla h             $CB, $24          2F                X                 X
	sla l             $CB, $25          2F                X                 X
	sla (hl)          $CB, $26          2F + 1R + 1W + 1  3F + 1R + 1W + 1  3F + 1R + 1W + 1
	sla (ix+n)        $DD, $CB, n, $26  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	sla (iy+n)        $FD, $CB, n, $26  4F + 1R + 1W + 1  5F + 1R + 1W + 1  5F + 1R + 1W + 1
	================  ================  ================  ================  ================

**Notes**
	- Unlike ``RL``, the initial state of the carry flag has no effect on the result of this instruction, so a number can be easily doubled without worrying about the state of the carry flag.
	- Despite the mnemonics, ``SLA`` has more in common with ``SRL`` (Shift Right Logical) than ``SRA`` (Shift Right Arithmetic). This is because ``SRA`` is intended for use with signed integers, whereas ``SLA`` and ``SRL`` are more useful with unsigned integers.

**See Also**
	`RL <rl.html>`_, `RLC <rlc.html>`_, `SRA <sra.html>`_, `SRL <srl.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
