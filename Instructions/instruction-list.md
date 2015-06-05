# AVR Instruction List

## Arithmetic and Logic Instructions

Mnemonic | Operands  | Description                                    |
:--------|:----------|:-----------------------------------------------|
`ADD`    | `Rd, Rr`  | Add without Carry
`ADC`    | `Rd, Rr`  | Add with Carry
`ADIW`   | `Rd, K`   | Add Immediate to Word
`SUB`    | `Rd, Rr`  | Subtract without Carry
`SUBI`   | `Rd, K`   | Subtract Immediate
`SBC `   | `Rd, Rr`  | Subtract with Carry
`SBCI`   | `Rd, K`   | Subtract Immediate with Carry
`SBIW`   | `Rd, K`   | Subtract Immediate from Word
`AND`    | `Rd, Rr`  | Logical AND
`ANDI`   | `Rd, K`   | Logical AND with Immediate
`OR`     | `Rd, Rr`  | Logical OR
`ORI`    | `Rd, K`   | Logical OR with Immediate
`EOR`    | `Rd, Rr`  | Exclusive OR
`COM`    | `Rd`      | One's Complement
`NEG`    | `Rd`      | Two's Complement
`SBR`    | `Rd,K`    | Set Bit(s) in Register
`CBR`    | `Rd,K`    | Clear Bit(s) in Register
`INC`    | `Rd`      | Increment
`DEC`    | `Rd`      | Decrement
`TST`    | `Rd`      | Test for Zero or Minus
`CLR`    | `Rd`      | Clear Register
`SER`    | `Rd`      | Set Register
`MUL`    | `Rd,Rr`   | Multiply Unsigned
`MULS`   | `Rd,Rr`   | Multiply Signed
`MULSU`  | `Rd,Rr`   | Multiply Signed with Unsigned
`FMUL`   | `Rd,Rr`   | Fractional Multiply Unsigned
`FMULS`  | `Rd,Rr`   | Fractional Multiply Signed
`FMULSU` | `Rd,Rr`   | Fractional Multiply Signed with Unsigned
`DES`    | `k`       | Data Encryption

## Branch Instructions

Mnemonic | Operands  | Description
:--------|:----------|:-----------------------------------------------|
`RJMP`   | `k`       | Relative Jump
`IJMP`   |           | Indirect Jump to (Z)
`EIJMP`  |           | Extended Indirect Jump to (Z)
`JMP`    | `k`       | Jump
`RCALL`  | `k`       | Relative Call Subroutine
`ICALL`  |           | Indirect Call to (Z)
`EICALL` |           | Extended Indirect Call to (Z)
`CALL`   | `k`       | Call Subroutine
`RET`    |           | Subroutine Return
`RETI`   |           | Interrupt Return
`CPSE`   | `Rd,Rr`   | Compare, Skip if Equal
`CP`     | `Rd,Rr`   | Compare
`CPC`    | `Rd,Rr`   | Compare with Carry
`CPI`    | `Rd,K `   | Compare with Immediate
`SBRC`   | `Rr, b`   | Skip if Bit in Register Cleared
`SBRS`   | `Rr, b`   | Skip if Bit in Register Set
`SBIC`   | `A, b`    | Skip if Bit in I/O Register Cleared
`SBIS`   | `A, b`    | Skip if Bit in I/O Register Set
`BRBS`   | `s, k`    | Branch if Status Flag Set
`BRBC`   | `s, k`    | Branch if Status Flag Cleared
`BREQ`   | `k`       | Branch if Equal
`BRNE`   | `k`       | Branch if Not Equal
`BRCS`   | `k`       | Branch if Carry Set
`BRCC`   | `k`       | Branch if Carry Cleared
`BRSH`   | `k`       | Branch if Same or Higher
`BRLO`   | `k`       | Branch if Lower
`BRMI`   | `k`       | Branch if Minus
`BRPL`   | `k`       | Branch if Plus
`BRGE`   | `k`       | Branch if Greater or Equal, Signed
`BRLT`   | `k`       | Branch if Less Than, Signed
`BRHS`   | `k`       | Branch if Half Carry Flag Set
`BRHC`   | `k`       | Branch if Half Carry Flag Cleared
`BRTS`   | `k`       | Branch if T Flag Set
`BRTC`   | `k`       | Branch if T Flag Cleared
`BRVS`   | `k`       | Branch if Overflow Flag is Set
`BRVC`   | `k`       | Branch if Overflow Flag is Cleared
`BRIE`   | `k`       | Branch if Interrupt Enabled
`BRID`   | `k`       | Branch if Interrupt Disabled

## Data Transfer Instructions

Mnemonic | Operands  | Description
:--------|:----------|:-----------------------------------------------|
`MOV`    | `Rd, Rr`  | Copy Register
`MOVW`   | `Rd, Rr`  | Copy Register Pair
`LDI`    | `Rd, K`   | Load Immediate
`LDS`    | `Rd, k`   | Load Direct from data space
`LD`     | `Rd, X`   | Load Indirect
`LD`     | `Rd, X+`  | Load Indirect and Post-Increment
`LD`     | `Rd, -X`  | Load Indirect and Pre-Decrement
`LD`     | `Rd, Y`   | Load Indirect
`LD`     | `Rd, Y+`  | Load Indirect and Post-Increment
`LD`     | `Rd, -Y`  | Load Indirect and Pre-Decrement
`LDD`    | `Rd,Y+q`  | Load Indirect with Displacement
`LD`     | `Rd, Z`   | Load Indirect
`LD`     | `Rd, Z+`  | Load Indirect and Post-Increment
`LD`     | `Rd, -Z`  | Load Indirect and Pre-Decrement
`LDD`    | `Rd, Z+q` | Load Indirect with Displacement
`STS`    | `k, Rr`   | Store Direct to data space
`ST`     | `X, Rr`   | Store Indirect
`ST`     | `X+, Rr`  | Store Indirect and Post-Increment
`ST`     | `-X, Rr`  | Store Indirect and Pre-Decrement
`ST`     | `Y, Rr`   | Store Indirect
`ST`     | `Y+, Rr`  | Store Indirect and Post-Increment
`ST`     | `-Y, Rr`  | Store Indirect and Pre-Decrement
`STD`    | `Y+q,Rr`  | Store Indirect with Displacement
`ST`     | `Z, Rr`   | Store Indirect
`ST`     | `Z+, Rr`  | Store Indirect and Post-Increment
`ST`     | `-Z, Rr`  | Store Indirect and Pre-Decrement
`STD`    | `Z+q,Rr`  | Store Indirect with Displacement
`LPM`    |           | Load Program Memory
`LPM`    | `Rd, Z`   | Load Program Memory
`LPM`    | `Rd, Z+`  | Load Program Memory and Post-Increment
`ELPM`   |           | Extended Load Program Memory
`ELPM`   | `Rd, Z`   | Extended Load Program Memory
`ELPM`   | `Rd, Z+`  | Extended Load Program Memory and Post-Increment
`SPM`    |           | Store Program Memory
`SPM`    | `Z+`      | Store Program Memory and Post-Increment by 2
`IN`     | `Rd, A`   | In From I/O Location
`OUT`    | `A, Rr`   | Out To I/O Location
`PUSH`   | `Rr`      | Push Register on Stack
`POP`    | `Rd`      | Pop Register from Stack
`XCH`    |  `Z, Rd`  | Exchange
`LAS`    |  `Z, Rd`  | Load and Set
`LAC`    |  `Z, Rd`  | Load and Clear
`LAT`    |  `Z, Rd`  | Load and Toggle

## Bit and Bit-test Instructions

Mnemonic | Operands  | Description
:--------|:----------|:-----------------------------------------------|
`LSL`    | `Rd`      |  Logical Shift Left
`LSR`    | `Rd`      | Logical Shift Right
`ROL`    | `Rd`      | Rotate Left Through Carry
`ROR`    | `Rd`      | Rotate Right Through Carry
`ASR`    | `Rd`      | Arithmetic Shift Right
`SWAP`   | `Rd`      | Swap Nibbles
`BSET`   | `s`       | Flag Set
`BCLR`   | `s`       | Flag Clear
`SBI`    | `A, b`    | Set Bit in I/O Register
`CBI`    | `A, b`    | Clear Bit in I/O Register
`BST`    | `Rr, b`   | Bit Store from Register to T
`BLD`    | `Rd, b`   | Bit load from T to Register
`SEC`    |           | Set Carry
`CLC`    |           | Clear Carry
`SEN`    |           | Set Negative Flag
`CLN`    |           | Clear Negative Flag
`SEZ`    |           | Set Zero Flag
`CLZ`    |           | Clear Zero Flag
`SEI`    |           | Global Interrupt Enable
`CLI`    |           | Global Interrupt Disable
`SES`    |           | Set Signed Test Flag
`CLS`    |           | Clear Signed Test Flag
`SEV`    |           | Set Two's Complement Overflow
`CLV`    |           | Clear Two's Complement Overflow
`SET`    |           | Set T in SREG
`CLT`    |           | Clear T in SREG
`SEH`    |           | Set Half Carry Flag in SREG
`CLH`    |           | Clear Half Carry Flag in SREG

## MCU Control Instructions

Mnemonic | Operands  | Description
:--------|:----------|:-----------------------------------------------|
`BREAK`  |           | Break
`NOP`    |           | No Operation
`SLEEP`  |           | Sleep
`WDR`    |           | Watchdog Reset
