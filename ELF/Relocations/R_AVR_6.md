
# The `R_AVR_6` ELF relocation

The `R_AVR_6` ELF relocation operates on the `LLD` and `STD` instructions.

The `LDD Rd, Z+q` instruction is as follows:

```
10q0 qq00 0000 0qqq
```
**NOTE**: The destination register (`Rd`) bits have been set to zero for simplicity.


