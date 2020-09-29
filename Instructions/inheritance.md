
# AVR Instruction Set Inheritance

This document attempts to describe inheritance in between MCU families.

Sources
* [en.wikipedia.org/wiki/Atmel_AVR_instruction_set](https://en.wikipedia.org/wiki/Atmel_AVR_instruction_set)
*  `gcc/config/avr/avr-mcus.def`

## Minimal Core (`avr1`)

* Arithmetic
  * `ADD  Rd, Rr`
  * `ADC  Rd, Rr`
  * `SUB  Rd, Rr`
  * `SUBI Rd, K`
  * `SBC  Rd, Rr`
  * `SBCI Rd, K`
  * `AND  Rd, Rr`
  * `ANDI Rd, K`
  * `OR   Rd, Rr`
  * `ORI  Rd, K`
  * `EOR  Rd, Rr`
  * `COM  Rd`
  * `NEG  Rd`
  * `SBR  Rd, K`
  * `CBR  Rd, K`
  * `INC  Rd`
  * `DEC  Rd`
  * `TST  Rd`
  * `CLR  Rd`
  * `SER  Rd`
* Branches
  * `RJMP  k`
  * `RCALL k`
  * `RET`
  * `RETI`
  * `CPSE Rd, Rr`
  * `CP   Rd, Rr`
  * `CPC  Rd, Rr`
  * `CPI  Rd, K`
  * `SBRC Rr, b`
  * `SBRS Rr, b`
  * `SBIC P, b`
  * `SBIS P. b`
  * `BRBS s, k`
  * `BRBC s, k`
  * `BREQ k`
  * `BRNE k`
  * `BRCS k`
  * `BRCC k`
  * `BRSH k`
  * `BRLO k`
  * `BRMI k`
  * `BRPL k`
  * `BRGE k`
  * `BRLT k`
  * `BRHS k`
  * `BRHC k`
  * `BRTS k`
  * `BRTC k`
  * `BRVS k`
  * `BRVC k`
  * `BRIE k`
  * `BRID k`
* Transfers
  * `LD Rd, Z`
  * `ST Z, Rr`
  * `MOV Rd, Rr`
  * `LDI Rd, K`
  * `IN  Rd, P`
  * `OUT P, Rr`
  * `LPM` (not in AT90S1200)
* Bitwise
  * `SBI  P, b`
  * `CBI  P, b`
  * `LSL  Rd`
  * `LSR  Rd`
  * `ROL  Rd`
  * `ROR  Rd`
  * `ASR  Rd`
  * `SWAP Rd`
  * `BSET s`
  * `BCLR s`
  * `BST  Rr, b`
  * `BLD  Rd, b`
  * `SEC`
  * `CLC`
  * `SEN`
  * `CLN`
  * `SEZ`
  * `CLZ`
  * `SEI`
  * `CLI`
  * `SES`
  * `CLS`
  * `SEV`
  * `CLV`
  * `SET`
  * `CLT`
  * `SEH`
  * `CLH`
* Special
  * `NOP`
  * `SLEEP`
  * `WDR`

## Classic core (space <= 8K) (`avr2`)

* Arithmetic
  * `ADIW Rd, K`
  * `SBIW Rd, K`
* Branches
  * `IJMP`
  * `ICALL`
* Transfers
  * `LD Rd, X`
  * `LD Rd, X+`
  * `LD Rd, -X`
  * `LD Rd, Y`
  * `LD Rd, Y+`
  * `LD Rd, -Y`
  * `LD Rd, Z`
  * `LD Rd, Z+`
  * `LD Rd, -Z`
  * `LDD Rd, Y+q`
  * `LDD Rd, Z+q`
  * `LDS Rd, K`
  * `ST X,  Rr`
  * `ST X+, Rr`
  * `ST -X, Rr`
  * `ST Y,  Rr`
  * `ST Y+, Rr`
  * `ST -Y, Rr`
  * `ST Z,  Rr`
  * `ST Z+, Rr`
  * `ST -Z, Rr`
  * `STD Y+q, Rr`
  * `STD Z+q, Rr`
  * `STS k, Rr`
  * `PUSH Rr`
  * `POP Rd`

## Classic core (space <= 8K) (with `MOVW Rd, Rr`) (`avr25`)

* Transfers
  * `MOVW Rd, Rr`

## Classic core (8K < space <= 64K) (`avr3`)

* Branches
  * `JMP k`
  * `CALL k`
* Transfers
  * `ELPM`

## Classic core (space == 128K) (`avr31`)

**TODO**: Document.

## Classic (with `MOVW Rd, Rr`, `JMP k`, `CALL k`) (`avr36`)

**TODO**: Document with what space size this is for.

* Branches
  * `JMP k`
  * `CALL k`
* Transfers
  * `MOVW Rd, Rr`

## Enhanced core (space <= 8K) (`avr4`)

* Arithmtic
  * `MUL    Rd, Rr`
  * `MULS   Rd, Rr`
  * `MULSU  Rd, Rr`
  * `FMUL   Rd, Rr`
  * `FMULS  Rd, Rr`
  * `FMULSU Rd, Rr`
* Transfers
  * `MOVW Rd, Rr`
  * `LPM Rd, Z`
  * `LPM Rd, Z+`
  * `SPM`

## Enhanced core (8K < space <= 64K) (`avr5`)

* Special
  * `BREAK`
* Branches
  * `EIJMP`
  * `EICALL`

## Enhanced core (space == 128K) (`avr51`)

* Transfers
  * `ELPM Rd, Z`
  * `ELPM Rd, Z+`

## 3-byte PC (`avr6`)

Referred to as `AVR_ISA_XMEGA` in `binutils/include/opcode/avr.h`.

* Transfers
  * `SPM Z+`

## XMEGA core

Referred to as `AVR_ISA_XMEGAU` in `binutils/include/opcode/avr.h`.

* Arithmetic
  * `DES k`
* Transfers
  * `XCH Z, Rd`
  * `LAS Z, Rd`
  * `LAC Z, Rd`
  * `LAT Z, Rd`
  * **NOTE**: These four transfer instructions are referred to as Read-Modify-Write (RMW).


## Reduced core (`avrtiny`)

The reduced core does not follow the standard inheritance pattern.

* Arithmetic
  * Identical to minimal core, except for fewer registers
* Branches
  * Identical to classic core (up to 8K), except for fewer registers.
* Transfers
  * Identical to classic core (up to 8K), except for:
    * LPM (removed)
    * LDD (removed)
    * STD (removed)
    * LD (also accessed program memory)
    * LDS (different machine encoding)
    * STS (different machine encoding)
  * Reduced register set.
* Bitwise
  * Identical to enhanced core with up to 128K, except for fewer registers
* Special
  * Identical to enhanced core with up to 128K, except for fewer registers

# Exceptions

* Some devices have an 8 bit stack pointer. That is to say that only SPL is used (as opposed to SPL and SPH).
* Skip Errata
  * Some devices have a core erratum when skipping a 2-word instruction. See `gcc/config/avr/avr-arch.h` for details.
