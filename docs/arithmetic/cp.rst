CP
--------

**CP M,N**
	Compare

**Description**
	| Subtracts ``N`` from ``M`` (and updates the flags accordingly), but doesn't modify either operand.
	| ``M - N``

**Uses**
	- Comparing two bytes

**Results**
	================    ==========================================
	Register/Flag       8-bit                                     
	================    ==========================================
	``S`` flag          Set if the result is negative; else reset
	``Z`` flag          Set if ``M`` = ``N``
	``H`` flag          Set if borrow from bit 4; else reset
	``P/V`` flag        Set if overflow; else reset
	``N`` flag          Set
	``C`` flag          Set if borrow; else reset
	================    ==========================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	cp a,a            $BF               1F                X                 X
	cp a,b            $B8               1F                X                 X
	cp a,c            $B9               1F                X                 X
	cp a,d            $BA               1F                X                 X
	cp a,e            $BB               1F                X                 X
	cp a,h            $BC               1F                X                 X
	cp a,l            $BD               1F                X                 X
	cp a,ixh          $DD, $BC          2F                X                 X
	cp a,ixl          $DD, $BD          2F                X                 X
	cp a,iyh          $FD, $BC          2F                X                 X
	cp a,iyl          $FD, $BD          2F                X                 X
	cp a,(hl)         $BE               1F + 1R           2F + 1R           2F + 1R
	cp a,(ix+n)       $DD, $BE, n       3F + 1R           4F + 1R           4F + 1R
	cp a,(iy+n)       $FD, $BE, n       3F + 1R           4F + 1R           4F + 1R
	cp a,n            $FE, n            2F                X                 X
	================  ================  ================  ================  ================

**Notes**
	- When using CP with signed integers, the flags are set as follows:
		- ``Z`` means ``M`` = ``N``
		- ``NZ`` means ``M`` ≠ ``N``
		- ``C`` means ``M`` < ``N``
		- ``NC`` means ``M`` ≥ ``N``

**See Also**
	`SUB <adc.html>`_, `SBC <sbc.html>`_, `CPI </en/latest/block-ops/cpi.html>`_, `CPIR </en/latest/block-ops/cpir.html>`_, `CPD </en/latest/block-ops/cpd.html>`_, `CPDR </en/latest/block-ops/cpdr.html>`_
