# LD/ST instructions

## Permutations
ld Rd, X    `1001 000d dddd 1100`
ld Rd, X+   `1001 000d dddd 1101`
ld Rd, -X   `1001 000d dddd 1110`

ld Rd, Y    `1000 000d dddd 1000`
ld Rd, Y+   `1001 000d dddd 1001`
ld Rd, -Y   `1001 000d dddd 1010`

ld Rd, Z    `1000 000d dddd 0000`
ld Rd, Z+   `1001 000d dddd 0001`
ld Rd, -Z   `1001 000d dddd 0010`
                bit is isX OR predec/postinc

General encoding:

`100r 000d dddd rrmm`

Where
  * `rrr` is the pointer register number
    * `111` => X
    * `
  * `ddddd` is the destination register
  * `mm` is the mode
    * `0b00` => normal (do not modify ptr register)
    * `0b01` => postinc
    * `0b10` => predec

