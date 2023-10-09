**These question are to be answered using [[Architecture and MIPS Case Study]],[[Compilation and Execution]],[[Computer Systems, CPU, Memory and Program Execution]],[[Floating Point Numbers]], and [[Numbers]]**
Question 1:

| Decimal | Binary      | Octal   | Hexadecimal |
| ------- | ----------- | ------- | ----------- |
| **33**  | 100001      | 41      | 21          |
|   117      | **1110101** |   165      |35|
|    451     |    111000011         | **703** |       1C3      |
|    431     |     110111111        |    677     | **1AF**     |

Row 1:
Binary:

| 33  | -   |
| --- | --- |
| 16  | 1   |
| 8   | 0   |
| 4   | 0   |
| 2   | 0   |
| 1   | 0   |
| 0    |1     |
Octal = 100,001 = 4,1
Hexadecimal = 0010,0001 2,1

Row 2:
Decimal = 1 + 4 + 16 + 32 + 64 = 117
Octal = 001,110,101 = 1,6,5
Hexadecimal = 0011,0101 = 3,5

Row 3:
Decimal = 3 + 0 + (7 x  64) = 448 + 3 = 451
Binary = 101,000,011 (225,1) (112,1) (56,0) (28,0) (14,0) (7,0) (3,1) (1,1) (0,1)
Hexadecimal = 0001,0100,0011 = 1,4,3

Row 4:
Decimal = 15 + (10 x 16) + (16 x 16) = 15 + 160 + 256 = 431
Binary = 0001,1011,1111
Octal = 110,111,111 = 6,7,7

Example Questions
1. The 32 bit (4 byte) value 101102103104 is used to represent the 4 ASCII characters "ABCD" in octal
	1.  Add 001002003004

| 1   | 0   | 1   | 1   | 0   | 2   | 1   | 0   | 3   | 1   | 0   | 4   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 1   | 0   | 0   | 2   | 0   | 0   | 3   | 0   | 0   | 4   |
|     1|     0|     2|     1|     0|     4|     1|     0|     6|     1|     1|0     |
		The answer is: 102104106110 in octal
		2. What would the interpretation of that result as ASCII characters
		A = 101 B =102 C = 103 D = 104
		New values are 102,104,106,110 which is BDFJ
2. If a floating point is represented in 8 bits. The leftmost bit represents the sign of the exponent, the next stage is the mantissa, the next 2 bits represent the magnitude of the exponent and the final four bits the magnitude of the mantissa.
	1. 1.741
			Binary = 1.10111 
			exponent = 1 + 127 = 128 = 10000000
			mantissa = 1011 1000 000
			010000000101110100000
	1.  17412241
			Binary = 1000010011011000010010001
			exponent = 24 + 127 = 251
			mantissa = 000010011011000010010001
		
