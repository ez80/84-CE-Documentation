DEC
--------

**DEC M**
	Decrement

**Description**
	| Decrements ``M`` by 1.
	| ``M -= 1``

**Results**
	================    =================================================  ==========================================  ========================================
	Register/Flag       8-bit                                              16-bit (non-ADL)                            24-bit (ADL)
	================    =================================================  ==========================================  ========================================
	``M``               Set to the result of ``M - 1``
	----------------    ---------------------------------------------------------------------------------------------------------------------------------------
	``S`` flag          Set if the result is negative; else reset          Not affected
	``Z`` flag          Set if the result is 0; else reset                 Not affected
	``H`` flag          Set if borrow from bit 4; else reset               Not affected
	``P/V`` flag        Set if ``M`` was $80 before operation; else reset  Not affected
	``N`` flag          Set                                                Not affected
	----------------    -------------------------------------------------  ------------------------------------------------------------------------------------
	``C`` flag          Not affected
	================    =======================================================================================================================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	dec a             $3D               1F                X                 X
	dec b             $05               1F                X                 X
	dec c             $0D               1F                X                 X
	dec d             $15               1F                X                 X
	dec e             $1D               1F                X                 X
	dec h             $25               1F                X                 X
	dec l             $2D               1F                X                 X
	dec ixh           $DD, $25          2F                X                 X
	dec ixl           $DD, $2D          2F                X                 X
	dec iyh           $FD, $25          2F                X                 X
	dec iyl           $FD, $2D          2F                X                 X
	dec (hl)          $86               1F + 1R + 1W + 1  2F + 1R + 1W + 1  2F + 1R + 1W + 1
	dec (ix+n)        $DD, $35, n       3F + 1R + 1W + 1  4F + 1R + 1W + 1  4F + 1R + 1W + 1
	dec (iy+n)        $FD, $35, n       3F + 1R + 1W + 1  4F + 1R + 1W + 1  4F + 1R + 1W + 1
	dec bc            $ED, $0B          1F                2F                2F
	dec de            $ED, $1B          1F                2F                2F
	dec hl            $ED, $2B          1F                2F                2F
	dec sp            $ED, $3B          1F                2F                2F
	dec ix            $DD, $2B          2F                3F                3F
	dec iy            $ED, $2B          2F                3F                3F
	================  ================  ================  ================  ================

**Notes**
	- While this instruction can be combined with a ``jr nz,LoopLabel`` to create a great 8-bit loop, using ``dec`` with a 16-bit or 24-bit operand will not alter the flags, so you'll need another method of checking if the register pair is zero.

**See Also**
	`INC </en/latest/is-inc.html>`_
