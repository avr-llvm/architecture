# AVR inline assembly constraints

Constraint | Used for                                                                  | Range
---------- | --------------------------------------------------------------------------|----------------------
a          | Simple upper registers                                                    | r16 to r23
b          | Base pointer registers pairs                                              | y, z
d          | Upper register                                                            | r16 to r31
e          | Pointer register pairs                                                    | x, y, z
q          | Stack pointer register                                                    | SPH:SPL
r          | Any register                                                              | r0 to r31
t          | Temporary register                                                        | r0
w          | Special upper register pairs                                              | r24, r26, r28, r30
x          | Pointer register pair X                                                   | x (r27:r26)
y          | Pointer register pair Y                                                   | y (r29:r28)
z          | Pointer register pair Z                                                   | z (r31:r30)
G          | Floating point constant                                                   | 0.0
I          | 6-bit positive integer constant                                           | 0 to 63
J          | 6-bit negative integer constant                                           | -63 to 0
K          | Integer constant                                                          | 2
L          | Integer constant                                                          | 0
l          | Lower registers                                                           | r0 to r15
M          | 8-bit integer constant                                                    | 0 to 255
N          | Integer constant                                                          | -1
O          | Integer constant                                                          | 8, 16, 24
P          | Integer constant                                                          | 1
Q          | A memory address based on Y or Z pointer with displacement                |
R          | Integer constant                                                          | -6 to 5
