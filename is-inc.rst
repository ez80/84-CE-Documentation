INC
--------

**INC M**
	Increment

**Description**
	| Increments ``M`` by 1.
	| ``M += 1``

**Results**
	================    =================================================  ==========================================  ========================================
	Register/Flag       8-bit                                              16-bit (non-ADL)                            24-bit (ADL)
	================    =================================================  ==========================================  ========================================
	``M``               Set to the result of ``M + 1``
	----------------    ---------------------------------------------------------------------------------------------------------------------------------------
	``S`` flag          Set if the result is negative; else reset          Not affected
	``Z`` flag          Set if the result is 0; else reset                 Not affected
	``H`` flag          Set if carry from bit 3; else reset                Not affected
	``P/V`` flag        Set if ``M`` was $7F before operation; else reset  Not affected
	``N`` flag          Reset                                              Not affected
	----------------    -------------------------------------------------  ------------------------------------------------------------------------------------
	``C`` flag          Not affected
	================    ================================================================================================================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	inc a             $3C               1F                X                 X
	inc b             $04               1F                X                 X
	inc c             $0C               1F                X                 X
	inc d             $14               1F                X                 X
	inc e             $1C               1F                X                 X
	inc h             $24               1F                X                 X
	inc l             $2C               1F                X                 X
	inc ixh           $DD, $24          2F                X                 X
	inc ixl           $DD, $2C          2F                X                 X
	inc iyh           $FD, $24          2F                X                 X
	inc iyl           $FD, $2C          2F                X                 X
	inc (hl)          $34               1F + 1R + 1W + 1  2F + 1R + 1W + 1  2F + 1R + 1W + 1
	inc (ix+n)        $DD, $34, n       3F + 1R + 1W + 1  4F + 1R + 1W + 1  4F + 1R + 1W + 1
	inc (iy+n)        $FD, $34, n       3F + 1R + 1W + 1  4F + 1R + 1W + 1  4F + 1R + 1W + 1
	inc bc            $ED, $0B          1F                2F                2F
	inc de            $ED, $1B          1F                2F                2F
	inc hl            $ED, $23          1F                2F                2F
	inc sp            $ED, $3B          1F                2F                2F
	inc ix            $DD, $23          2F                3F                3F
	inc iy            $ED, $23          2F                3F                3F
	================  ================  ================  ================  ================

**Notes**
	- Keep in mind that the flags are not altered when using this instruction with a 16-bit and 24-bit operand.

**See Also**
	`DEC </en/latest/is-dec.html>`_
