=======================
Arithmetic Instructions
=======================





ADC
--------

**ADC M,N**
	Add with carry

**Description**
	Adds ``M``, ``N``, and the carry flag (+0 or +1) and stores the result in ``M``.
	``M += N + Carry``

**Uses**
	Storing the state of the carry flag in either ``A`` or ``HL``  with ``adc a,0`` or ``ld bc/de,0 \ adc hl,bc/de``. Can be useful otherwise in very specific situations.

**Results**

	================	==========================================	==========================================	========================================
	Register/Flag		8-bit										16-bit (non-ADL)							24-bit (ADL)
	``M``				Set to the result of ``M + N + Carry``
	================	==========================================  ==========================================  ========================================
	``S`` flag			Set if the result is negative; else reset
	``Z`` flag			Set if the result is 0; else reset
	----------------	--------------------------------------------------------------------------------------------------------------------------------
	``H`` flag			Set if carry from bit 3; else reset			Set if carry from bit 11; else reset
	----------------	------------------------------------------	------------------------------------------------------------------------------------
	``P/V`` flag		Set if overflow; else reset
	``N`` flag			Reset
	----------------	--------------------------------------------------------------------------------------------------------------------------------
	``C`` flag			Set if carry from bit 7; else reset			Set if carry from bit 15; else reset		Set if carry from bit 23; else reset
	================	==========================================	==========================================	========================================

**Allowed Instructions**
	================	================	==================	==================	==================
	Instruction			Opcode				CC (ADL/non-ADL)	CC (.S)				CC (.L)
	adc a,a				$8F					1F					X					X
	adc a,b				$88					1F					X					X
	adc a,c				$89					1F					X					X
	adc a,d				$8A					1F					X					X
	adc a,e				$8B					1F					X					X
	adc a,h				$8C					1F					X					X
	adc a,l				$8D					1F					X					X
	adc a,ixh			$DD, $8C			2F					X					X
	adc a,ixl			$DD, $8D			2F					X					X
	adc a,iyh			$FD, $8C			2F					X					X
	adc a,iyl			$FD, $8D			2F					X					X
	adc a,(hl)			$8E					1F + 1R				2F + 1R				2F + 1R
	adc a,(ix+n)		$DD, $8E, n			3F + 1R				4F + 1R				4F + 1R
	adc a,(iy+n)		$FD, $8E, n			3F + 1R				4F + 1R				4F + 1R
	adc a,n				$CE, n				2F					X					X
	adc hl,bc			$ED, $4A			2F					3F					3F
	adc hl,de			$ED, $5A			2F					3F					3F
	adc hl,hl			$ED, $6A			2F					3F					3F
	adc hl,sp			$ED, $7A			2F					3F					3F
	================	================	==================	==================	==================

**See Also**
	ADD, SBC, SUB





ADD
--------
