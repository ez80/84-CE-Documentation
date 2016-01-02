SET
--------

**SET b,M**
	Set Bit

**Description**
	| Sets the ``b``th bit of ``M`` to one. ``b`` must be a hard-coded  number between 0 and 7.

**Results**
	================    ==========================================  ==========================================  ========================================
	Register/Flag       8-bit                                       16-bit (non-ADL)                            24-bit (ADL)
	================    ==========================================  ==========================================  ========================================
	``M``               The ``b``th bit of M is set to one
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
	set 0,a           $CB, $C7          2F                X                 X
	set 0,b           $CB, $C0          2F                X                 X
	set 0,c           $CB, $C1          2F                X                 X
	set 0,d           $CB, $C2          2F                X                 X
	set 0,e           $CB, $C3          2F                X                 X
	set 0,h           $CB, $C4          2F                X                 X
	set 0,l           $CB, $C5          2F                X                 X
	set 0,(hl)        $CB, $C6          Unknown           Unknown           Unknown
	set 0,(ix+n)      $DD, $CB, $C6, n  Unknown           Unknown           Unknown
	set 0,(iy+n)      $FD, $CB, $C6, n  Unknown           Unknown           Unknown
	set 1,a           $CB, $CF          2F                X                 X
	set 1,b           $CB, $C8          2F                X                 X
	set 1,c           $CB, $C9          2F                X                 X
	set 1,d           $CB, $CA          2F                X                 X
	set 1,e           $CB, $CB          2F                X                 X
	set 1,h           $CB, $CC          2F                X                 X
	set 1,l           $CB, $CD          2F                X                 X
	set 1,(hl)        $CB, $CE          Unknown           Unknown           Unknown
	set 1,(ix+n)      $DD, $CB, $CE, n  Unknown           Unknown           Unknown
	set 1,(iy+n)      $FD, $CB, $CE, n  Unknown           Unknown           Unknown
	set 2,a           $CB, $D7          2F                X                 X
	set 2,b           $CB, $D0          2F                X                 X
	set 2,c           $CB, $D1          2F                X                 X
	set 2,d           $CB, $D2          2F                X                 X
	set 2,e           $CB, $D3          2F                X                 X
	set 2,h           $CB, $D4          2F                X                 X
	set 2,l           $CB, $D5          2F                X                 X
	set 2,(hl)        $CB, $D6          Unknown           Unknown           Unknown
	set 2,(ix+n)      $DD, $CB, $D6, n  Unknown           Unknown           Unknown
	set 2,(iy+n)      $FD, $CB, $D6, n  Unknown           Unknown           Unknown
	set 3,a           $CB, $DF          2F                X                 X
	set 3,b           $CB, $D8          2F                X                 X
	set 3,c           $CB, $D9          2F                X                 X
	set 3,d           $CB, $DA          2F                X                 X
	set 3,e           $CB, $DB          2F                X                 X
	set 3,h           $CB, $DC          2F                X                 X
	set 3,l           $CB, $DD          2F                X                 X
	set 3,(hl)        $CB, $DE          Unknown           Unknown           Unknown
	set 3,(ix+n)      $DD, $CB, $DE, n  Unknown           Unknown           Unknown
	set 3,(iy+n)      $FD, $CB, $DE, n  Unknown           Unknown           Unknown
	set 4,a           $CB, $E7          2F                X                 X
	set 4,b           $CB, $E0          2F                X                 X
	set 4,c           $CB, $E1          2F                X                 X
	set 4,d           $CB, $E2          2F                X                 X
	set 4,e           $CB, $E3          2F                X                 X
	set 4,h           $CB, $E4          2F                X                 X
	set 4,l           $CB, $E5          2F                X                 X
	set 4,(hl)        $CB, $E6          Unknown           Unknown           Unknown
	set 4,(ix+n)      $DD, $CB, $E6, n  Unknown           Unknown           Unknown
	set 4,(iy+n)      $FD, $CB, $E6, n  Unknown           Unknown           Unknown
	set 5,a           $CB, $EF          2F                X                 X
	set 5,b           $CB, $E8          2F                X                 X
	set 5,c           $CB, $E9          2F                X                 X
	set 5,d           $CB, $EA          2F                X                 X
	set 5,e           $CB, $EB          2F                X                 X
	set 5,h           $CB, $EC          2F                X                 X
	set 5,l           $CB, $ED          2F                X                 X
	set 5,(hl)        $CB, $EE          Unknown           Unknown           Unknown
	set 5,(ix+n)      $DD, $CB, $EE, n  Unknown           Unknown           Unknown
	set 5,(iy+n)      $FD, $CB, $EE, n  Unknown           Unknown           Unknown
	set 6,a           $CB, $F7          2F                X                 X
	set 6,b           $CB, $F0          2F                X                 X
	set 6,c           $CB, $F1          2F                X                 X
	set 6,d           $CB, $F2          2F                X                 X
	set 6,e           $CB, $F3          2F                X                 X
	set 6,h           $CB, $F4          2F                X                 X
	set 6,l           $CB, $F5          2F                X                 X
	set 6,(hl)        $CB, $F6          Unknown           Unknown           Unknown
	set 6,(ix+n)      $DD, $CB, $F6, n  Unknown           Unknown           Unknown
	set 6,(iy+n)      $FD, $CB, $F6, n  Unknown           Unknown           Unknown
	set 7,a           $CB, $FF          2F                X                 X
	set 7,b           $CB, $F8          2F                X                 X
	set 7,c           $CB, $F9          2F                X                 X
	set 7,d           $CB, $FA          2F                X                 X
	set 7,e           $CB, $FB          2F                X                 X
	set 7,h           $CB, $FC          2F                X                 X
	set 7,l           $CB, $FD          2F                X                 X
	set 7,(hl)        $CB, $FE          Unknown           Unknown           Unknown
	set 7,(ix+n)      $DD, $CB, $FE, n  Unknown           Unknown           Unknown
	set 7,(iy+n)      $FD, $CB, $FE, n  Unknown           Unknown           Unknown
	================  ================  ================  ================  ================

**Notes**
	- Interestingly enough, the index registers ``IXH``, ``IXL``, ``IYH``, and ``IYL`` cannot be used in this instruction, yet ``(IX+n)`` and ``(IY+n)`` are allowed as operands.

**See Also**
	`BIT </en/latest/is-bit.html>`_, `RES </en/latest/is-res.html>`_
