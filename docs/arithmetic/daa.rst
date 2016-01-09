DAA
--------

**DAA**
	Decimal Adjust Accumulator

**Description**
	| Does cool stuff with binary-coded decimal.

**Uses**
	- Probably useful for BCD arithmetic?

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
	`ADD <add.html>`_, `ADC <adc.html>`_, `RLD </en/latest/docs/bit-shifts/rld.html>`_, `RRD </en/latest/docs/bit-shifts/rrd.html>`_, `SBC <sbc.html>`_, `SUB <sub.html>`_

.. _parity: https://en.wikipedia.org/wiki/Parity_bit
