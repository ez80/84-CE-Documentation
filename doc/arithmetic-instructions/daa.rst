DAA
--------

**DAA**
	Decimal Adjust Accumulator

**Description**
	| Does cool stuff with binary-coded decimal. (Please someone tell me how this works???)

**Uses**
	- Probably useful for BCD arithmetic, but I'm not sure quite how.

**Results**
	================    ==============================================
	Register/Flag       8-bit
	================    ==============================================
	``S`` flag          Set to the 7th bit of the result
	``Z`` flag          Set if the result is 0; else reset
	``H`` flag          Really complicated
	``P/V`` flag        Set if the result has even parity_; else reset
	``N`` flag          Not affected
	``C`` flag          Really complicated
	================    ==============================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	daa               $27               1F                X                 X
	================  ================  ================  ================  ================

**Notes**
	- When using CP with signed integers, the flags are set as follows:
		- ``Z`` means ``M`` = ``N``
		- ``NZ`` means ``M`` ≠ ``N``
		- ``C`` means ``M`` < ``N``
		- ``NC`` means ``M`` ≥ ``N``

**See Also**
	`ADD </en/latest/is-add.html>`_, `ADC </en/latest/is-adc.html>`_, `SBC </en/latest/is-sbc.html>`_, `SUB </en/latest/is-sub.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
