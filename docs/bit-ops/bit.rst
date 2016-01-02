BIT
--------

**BIT b,M**
	Test Bit

**Description**
	| Checks the ``b``th bit of ``M`` and stores the inverse in the ``Z`` flag. ``b`` must be a hard-coded  number between 0 and 7.

**Results**
	================    ==========================================  ==========================================  ========================================
	Register/Flag       8-bit                                       16-bit (non-ADL)                            24-bit (ADL)
	================    ==========================================  ==========================================  ========================================
	``S`` flag          Undefined
	``Z`` flag          Set if bit ``b`` of ``M`` is zero
	``H`` flag          Set
	``P/V`` flag        Undefined
	``N`` flag          Reset
	``C`` flag          Not affected
	================    ================================================================================================================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	bit 0,a           $CB, $47          2F                X                 X
	bit 0,b           $CB, $40          2F                X                 X
	bit 0,c           $CB, $41          2F                X                 X
	bit 0,d           $CB, $42          2F                X                 X
	bit 0,e           $CB, $43          2F                X                 X
	bit 0,h           $CB, $44          2F                X                 X
	bit 0,l           $CB, $45          2F                X                 X
	bit 0,(hl)        $CB, $46          2F + 1R           3F + 1R           3F + 1R
	bit 0,(ix+n)      $DD, $CB, n, $46  4F + 1R           5F + 1R           5F + 1R
	bit 0,(iy+n)      $FD, $CB, n, $46  4F + 1R           5F + 1R           5F + 1R
	bit 1,a           $CB, $4F          2F                X                 X
	bit 1,b           $CB, $48          2F                X                 X
	bit 1,c           $CB, $49          2F                X                 X
	bit 1,d           $CB, $4A          2F                X                 X
	bit 1,e           $CB, $4B          2F                X                 X
	bit 1,h           $CB, $4C          2F                X                 X
	bit 1,l           $CB, $4D          2F                X                 X
	bit 1,(hl)        $CB, $4E          2F + 1R           3F + 1R           3F + 1R
	bit 1,(ix+n)      $DD, $CB, n, $4E  4F + 1R           5F + 1R           5F + 1R
	bit 1,(iy+n)      $FD, $CB, n, $4E  4F + 1R           5F + 1R           5F + 1R
	bit 2,a           $CB, $57          2F                X                 X
	bit 2,b           $CB, $50          2F                X                 X
	bit 2,c           $CB, $51          2F                X                 X
	bit 2,d           $CB, $52          2F                X                 X
	bit 2,e           $CB, $53          2F                X                 X
	bit 2,h           $CB, $54          2F                X                 X
	bit 2,l           $CB, $55          2F                X                 X
	bit 2,(hl)        $CB, $56          2F + 1R           3F + 1R           3F + 1R
	bit 2,(ix+n)      $DD, $CB, n, $56  4F + 1R           5F + 1R           5F + 1R
	bit 2,(iy+n)      $FD, $CB, n, $56  4F + 1R           5F + 1R           5F + 1R
	bit 3,a           $CB, $5F          2F                X                 X
	bit 3,b           $CB, $58          2F                X                 X
	bit 3,c           $CB, $59          2F                X                 X
	bit 3,d           $CB, $5A          2F                X                 X
	bit 3,e           $CB, $5B          2F                X                 X
	bit 3,h           $CB, $5C          2F                X                 X
	bit 3,l           $CB, $5D          2F                X                 X
	bit 3,(hl)        $CB, $5E          2F + 1R           3F + 1R           3F + 1R
	bit 3,(ix+n)      $DD, $CB, n, $5E  4F + 1R           5F + 1R           5F + 1R
	bit 3,(iy+n)      $FD, $CB, n, $5E  4F + 1R           5F + 1R           5F + 1R
	bit 4,a           $CB, $67          2F                X                 X
	bit 4,b           $CB, $60          2F                X                 X
	bit 4,c           $CB, $61          2F                X                 X
	bit 4,d           $CB, $62          2F                X                 X
	bit 4,e           $CB, $63          2F                X                 X
	bit 4,h           $CB, $64          2F                X                 X
	bit 4,l           $CB, $65          2F                X                 X
	bit 4,(hl)        $CB, $66          2F + 1R           3F + 1R           3F + 1R
	bit 4,(ix+n)      $DD, $CB, n, $66  4F + 1R           5F + 1R           5F + 1R
	bit 4,(iy+n)      $FD, $CB, n, $66  4F + 1R           5F + 1R           5F + 1R
	bit 5,a           $CB, $6F          2F                X                 X
	bit 5,b           $CB, $68          2F                X                 X
	bit 5,c           $CB, $69          2F                X                 X
	bit 5,d           $CB, $6A          2F                X                 X
	bit 5,e           $CB, $6B          2F                X                 X
	bit 5,h           $CB, $6C          2F                X                 X
	bit 5,l           $CB, $6D          2F                X                 X
	bit 5,(hl)        $CB, $6E          2F + 1R           3F + 1R           3F + 1R
	bit 5,(ix+n)      $DD, $CB, n, $6E  4F + 1R           5F + 1R           5F + 1R
	bit 5,(iy+n)      $FD, $CB, n, $6E  4F + 1R           5F + 1R           5F + 1R
	bit 6,a           $CB, $77          2F                X                 X
	bit 6,b           $CB, $70          2F                X                 X
	bit 6,c           $CB, $71          2F                X                 X
	bit 6,d           $CB, $72          2F                X                 X
	bit 6,e           $CB, $73          2F                X                 X
	bit 6,h           $CB, $74          2F                X                 X
	bit 6,l           $CB, $75          2F                X                 X
	bit 6,(hl)        $CB, $76          2F + 1R           3F + 1R           3F + 1R
	bit 6,(ix+n)      $DD, $CB, n, $76  4F + 1R           5F + 1R           5F + 1R
	bit 6,(iy+n)      $FD, $CB, n, $76  4F + 1R           5F + 1R           5F + 1R
	bit 7,a           $CB, $7F          2F                X                 X
	bit 7,b           $CB, $78          2F                X                 X
	bit 7,c           $CB, $79          2F                X                 X
	bit 7,d           $CB, $7A          2F                X                 X
	bit 7,e           $CB, $7B          2F                X                 X
	bit 7,h           $CB, $7C          2F                X                 X
	bit 7,l           $CB, $7D          2F                X                 X
	bit 7,(hl)        $CB, $7E          2F + 1R           3F + 1R           3F + 1R
	bit 7,(ix+n)      $DD, $CB, n, $7E  4F + 1R           5F + 1R           5F + 1R
	bit 7,(iy+n)      $FD, $CB, n, $7E  4F + 1R           5F + 1R           5F + 1R
	================  ================  ================  ================  ================

**Notes**
	- Interestingly enough, the index registers ``IXH``, ``IXL``, ``IYH``, and ``IYL`` cannot be used in this instruction, yet ``(IX+n)`` and ``(IY+n)`` are allowed as operands.
	- The ``Z`` flag is set as follows:
		- ``Z`` means the bit is **zero**
		- ``NZ`` means the bit is **one** (non-zero)

**See Also**
	`RES <res.html>`_, `SET <set.html>`_
