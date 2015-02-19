# AVR PC relative relocations

There are two program counter (PC) relative AVR relocations.

* `R_AVR_7_PCREL`
* `R_AVR_13_PCREL`

Both of these relocations operate on 16-bit branching instructions.

Because of this, the relocation target is offset by +16 bits.
It must be manually adjusted by subtracting two from the target.

Before applying either of these relocations, the target must also
be rightshifted by one digit. This is because in AVR, all instructions
have sizes which are even numbers (2/4 bytes). A property of all even binary numbers
is that they all have a zero in the least significant bit.

Because all of the PC-relative relocations address specific instructions at even addresses,
we are wasting a bit if we encode the always-zero bit into the relocation. Because of this,
all AVR PC relative relocations are rightshifted by 1, giving us one more bit for the address.

## `R_AVR_7_PCREL`

It is used solely by the 16-bit relative branch instructions.

This is the format of the `BRNE k` instruction:

```
1111 01kk kkkk k001
```

All of the other 16-bit relative branch instructions follow the same format (except different
sub-opcodes).

`R_AVR_7_PCREL` is used to relocate the target bits for these instructions during linking.

## `R_AVR_13_PCREL`

It is used solely by the 16-bit relative jump/call instructions.

This is the format of the `RJMP k` instruction:

```
1100 kkkk kkkk kkkk
```
