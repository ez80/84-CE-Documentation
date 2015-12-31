ADD
--------

**ADD M,N**
	Add

**Description**
	| Adds ``M`` and ``N`` and stores the result in ``M``.
	| ``M += N``

**Uses**
	- Adding two numbers together

**Results**
	================    ==========================================  ==========================================  ========================================
	Register/Flag       8-bit                                       16-bit (non-ADL)                            24-bit (ADL)
	================    ==========================================  ==========================================  ========================================
	``M``               Set to the result of ``M + N``
	----------------    --------------------------------------------------------------------------------------------------------------------------------
	``S`` flag          Set if the result is negative; else reset   Not affected
	``Z`` flag          Set if the result is 0; else reset          Not affected
	``H`` flag          Set if carry from bit 3; else reset         Set if carry from bit 11; else reset
	``P/V`` flag        Set if overflow; else reset                 Not affected
	----------------    ------------------------------------------  ------------------------------------------------------------------------------------
	``N`` flag          Reset
	----------------    --------------------------------------------------------------------------------------------------------------------------------
	``C`` flag          Set if carry from bit 7; else reset         Set if carry from bit 15; else reset        Set if carry from bit 23; else reset
	================    ==========================================  ==========================================  ========================================

**Allowed Instructions**
	================  ================  ==================  ==================  ==================
	Instruction       Opcode              CC (ADL/non-ADL)    CC (.S)             CC (.L)
	================  ================  ==================  ==================  ==================
	add a,a           $87               1F                  X                   X
	add a,b           $80               1F                  X                   X
	add a,c           $81               1F                  X                   X
	add a,d           $82               1F                  X                   X
	add a,e           $83               1F                  X                   X
	add a,h           $84               1F                  X                   X
	add a,l           $85               1F                  X                   X
	add a,ixh         $DD, $84          2F                  X                   X
	add a,ixl         $DD, $85          2F                  X                   X
	add a,iyh         $FD, $84          2F                  X                   X
	add a,iyl         $FD, $85          2F                  X                   X
	add a,(hl)        $86               1F + 1R             2F + 1R             2F + 1R
	add a,(ix+n)      $DD, $86, n       3F + 1R             4F + 1R             4F + 1R
	add a,(iy+n)      $FD, $86, n       3F + 1R             4F + 1R             4F + 1R
	add a,n           $C6, n            2F                  X                   X
	add hl,bc         $ED, $0A          2F                  3F                  3F
	add hl,de         $ED, $1A          2F                  3F                  3F
	add hl,hl         $ED, $2A          2F                  3F                  3F
	add hl,sp         $ED, $3A          2F                  3F                  3F
	add ix,bc         $DD, $0A          2F                  3F                  3F
	add ix,de         $DD, $1A          2F                  3F                  3F
	add ix,ix         $DD, $2A          2F                  3F                  3F
	add ix,sp         $DD, $3A          2F                  3F                  3F
	add iy,bc         $ED, $0A          2F                  3F                  3F
	add iy,de         $ED, $1A          2F                  3F                  3F
	add iy,iy         $ED, $2A          2F                  3F                  3F
	add iy,sp         $ED, $3A          2F                  3F                  3F
	================  ================  ==================  ==================  ==================

**Notes**
	- Unlike `ADC </en/latest/is-adc.html>`_, this instruction **does** support using the index registers IX and IY as the first operand. This is the only difference in the allowed instructions between the two.
	- This instruction **does not** modify the ``S``, ``Z``, and ``P/V`` flags when doing 16-bit and 24-bit addition. For that, you can use `ADC </en/latest/is-adc.html>`_.
	- Like most instructions, HL, IX, and IY are mutually exclusive. I.e. they cannot be used in the same instructions.

**See Also**
	`ADC </en/latest/is-adc.html>`_, `SBC </en/latest/is-sbc.html>`_, `SUB </en/latest/is-sub.html>`_
