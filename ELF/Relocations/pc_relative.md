# AVR PC relative relocations

There are two program counter (PC) relative AVR relocations.

* `R_AVR_7_PCREL`
* `R_AVR_13_PCREL`

Both of these relocations operate on 16-bit branching instructions.

Because of this, the relocation target is offset by +16 bits.
It must be manually adjusted by subtracting two from the target.

Before applying either of these relocations, the target must also
be rightshifted by one digit.

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

TODO

