RES
--------

**RES b,M**
	Reset Bit

**Description**
	| Sets the ``b``th bit of ``M`` to zero. ``b`` must be a hard-coded  number between 0 and 7.

**Results**
	================    ==========================================  ==========================================  ========================================
	Register/Flag       8-bit                                       16-bit (non-ADL)                            24-bit (ADL)
	================    ==========================================  ==========================================  ========================================
	``M``               The ``b``th bit of M is set to zero
	``S`` flag          Not affected
	``Z`` flag          Not affected
	``H`` flag          Not affected
	``P/V`` flag        Not affected
	``N`` flag          Not affected
	``C`` flag          Not affected
	================    ================================================================================================================================

**Allowed Instructions**
	================  ================  ================  ================  ================
	Instruction       Opcode            CC (ADL/non-ADL)  CC (.S)           CC (.L)
	================  ================  ================  ================  ================
	res 0,a           $CB, $87          2F                X                 X
	res 0,b           $CB, $80          2F                X                 X
	res 0,c           $CB, $81          2F                X                 X
	res 0,d           $CB, $82          2F                X                 X
	res 0,e           $CB, $83          2F                X                 X
	res 0,h           $CB, $84          2F                X                 X
	res 0,l           $CB, $85          2F                X                 X
	res 0,(hl)        $CB, $86          Unknown           Unknown           Unknown
	res 0,(ix+n)      $DD, $CB, $86, n  Unknown           Unknown           Unknown
	res 0,(iy+n)      $FD, $CB, $86, n  Unknown           Unknown           Unknown
	res 1,a           $CB, $8F          2F                X                 X
	res 1,b           $CB, $88          2F                X                 X
	res 1,c           $CB, $89          2F                X                 X
	res 1,d           $CB, $8A          2F                X                 X
	res 1,e           $CB, $8B          2F                X                 X
	res 1,h           $CB, $8C          2F                X                 X
	res 1,l           $CB, $8D          2F                X                 X
	res 1,(hl)        $CB, $8E          Unknown           Unknown           Unknown
	res 1,(ix+n)      $DD, $CB, $8E, n  Unknown           Unknown           Unknown
	res 1,(iy+n)      $FD, $CB, $8E, n  Unknown           Unknown           Unknown
	res 2,a           $CB, $97          2F                X                 X
	res 2,b           $CB, $90          2F                X                 X
	res 2,c           $CB, $91          2F                X                 X
	res 2,d           $CB, $92          2F                X                 X
	res 2,e           $CB, $93          2F                X                 X
	res 2,h           $CB, $94          2F                X                 X
	res 2,l           $CB, $95          2F                X                 X
	res 2,(hl)        $CB, $96          Unknown           Unknown           Unknown
	res 2,(ix+n)      $DD, $CB, $96, n  Unknown           Unknown           Unknown
	res 2,(iy+n)      $FD, $CB, $96, n  Unknown           Unknown           Unknown
	res 3,a           $CB, $9F          2F                X                 X
	res 3,b           $CB, $98          2F                X                 X
	res 3,c           $CB, $99          2F                X                 X
	res 3,d           $CB, $9A          2F                X                 X
	res 3,e           $CB, $9B          2F                X                 X
	res 3,h           $CB, $9C          2F                X                 X
	res 3,l           $CB, $9D          2F                X                 X
	res 3,(hl)        $CB, $9E          Unknown           Unknown           Unknown
	res 3,(ix+n)      $DD, $CB, $9E, n  Unknown           Unknown           Unknown
	res 3,(iy+n)      $FD, $CB, $9E, n  Unknown           Unknown           Unknown
	res 4,a           $CB, $A7          2F                X                 X
	res 4,b           $CB, $A0          2F                X                 X
	res 4,c           $CB, $A1          2F                X                 X
	res 4,d           $CB, $A2          2F                X                 X
	res 4,e           $CB, $A3          2F                X                 X
	res 4,h           $CB, $A4          2F                X                 X
	res 4,l           $CB, $A5          2F                X                 X
	res 4,(hl)        $CB, $A6          Unknown           Unknown           Unknown
	res 4,(ix+n)      $DD, $CB, $A6, n  Unknown           Unknown           Unknown
	res 4,(iy+n)      $FD, $CB, $A6, n  Unknown           Unknown           Unknown
	res 5,a           $CB, $AF          2F                X                 X
	res 5,b           $CB, $A8          2F                X                 X
	res 5,c           $CB, $A9          2F                X                 X
	res 5,d           $CB, $AA          2F                X                 X
	res 5,e           $CB, $AB          2F                X                 X
	res 5,h           $CB, $AC          2F                X                 X
	res 5,l           $CB, $AD          2F                X                 X
	res 5,(hl)        $CB, $AE          Unknown           Unknown           Unknown
	res 5,(ix+n)      $DD, $CB, $AE, n  Unknown           Unknown           Unknown
	res 5,(iy+n)      $FD, $CB, $AE, n  Unknown           Unknown           Unknown
	res 6,a           $CB, $B7          2F                X                 X
	res 6,b           $CB, $B0          2F                X                 X
	res 6,c           $CB, $B1          2F                X                 X
	res 6,d           $CB, $B2          2F                X                 X
	res 6,e           $CB, $B3          2F                X                 X
	res 6,h           $CB, $B4          2F                X                 X
	res 6,l           $CB, $B5          2F                X                 X
	res 6,(hl)        $CB, $B6          Unknown           Unknown           Unknown
	res 6,(ix+n)      $DD, $CB, $B6, n  Unknown           Unknown           Unknown
	res 6,(iy+n)      $FD, $CB, $B6, n  Unknown           Unknown           Unknown
	res 7,a           $CB, $BF          2F                X                 X
	res 7,b           $CB, $B8          2F                X                 X
	res 7,c           $CB, $B9          2F                X                 X
	res 7,d           $CB, $BA          2F                X                 X
	res 7,e           $CB, $BB          2F                X                 X
	res 7,h           $CB, $BC          2F                X                 X
	res 7,l           $CB, $BD          2F                X                 X
	res 7,(hl)        $CB, $BE          Unknown           Unknown           Unknown
	res 7,(ix+n)      $DD, $CB, $BE, n  Unknown           Unknown           Unknown
	res 7,(iy+n)      $FD, $CB, $BE, n  Unknown           Unknown           Unknown
	================  ================  ================  ================  ================

**Notes**
	- Interestingly enough, the index registers ``IXH``, ``IXL``, ``IYH``, and ``IYL`` cannot be used in this instruction, yet ``(IX+n)`` and ``(IY+n)`` are allowed as operands.

**See Also**
	`BIT </en/latest/is-bit.html>`_, `SET </en/latest/is-set.html>`_
