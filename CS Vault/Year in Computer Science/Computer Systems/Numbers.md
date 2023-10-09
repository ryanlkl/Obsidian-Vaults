# What are Computers Made of?
Computers consists of multiple "switches" called transistors

![[Pasted image 20230929153559.png]]

These switches can be turned **"on"** or **"off"** which is represented using **"1"** and **"0"** respectively.
All data must be represented using these binary digits - **bits**.

Using binary is:
- Cheaper
- More reliable
- Faster

**ASCII** and **Unicode** is used to represent characters when converting to machine code.

| System  | Base | Symbols | Used by people? | Used in computers? |
| ------- | ---- | ------- | --------------- | ------------------ |
| Decimal | 10   | 0->9    | Yes             | No                 |
| Binary  | 2    | 0,1     | No              | Yes                |
| Octal   | 8    | 0->7    | No              | No                 |
| Hexa-decimal        |16      |0->9,A->F         |No                 |No                    |

## Conversions
### Decimal to Binary
Divide by 2 and keep track of the remainder

| Step | Number | Remainder |
| ---- | ------ | --------- |
| 1    | 125    | -         |
| 2    | 62     | 1         |
| 3    | 31     | 0         |
| 4    | 15     | 1         |
| 5    | 7      | 1         |
| 6    | 3      | 1         |
| 7     |1        |1           |

### Binary to Decimal
From right to left, multiply value by 2$^n$ and add together, starting at 0 and incrementing by 1

| 2$^5$ | 2$^4$ | 2$^3$ | 2$^2$ | 2$^1$ | 2$^0$ |
| --- | --- | --- | --- | --- | --- |
| 1   | 0   | 1   | 0   | 1   | 1   |
| 32    |0     |8     |0     |2     |1     |

101011 = 32 + 8 + 2 + 1 = 43
### Decimal to Octal
Divide by 8 and keep track of the remainder

| Step | Number | Remainder |
| ---- | ------ | --------- |
| 1    | 1234   | -         |
| 2    | 154    | 2         |
| 3    | 19     | 2         |
| 4    | 2      | 3         |
| 5     |0        |2           |

### Octal to Decimal
From right to left, multiply value by 8$^n$ and add together, starting at 0 and incrementing by 1

| 8$^2$ | 8$^1$ | 8$^0$ |
| ----- | ----- | ----- |
| 7     | 2     | 4     |
| 448   | 16    | 4     |

724 = 448 + 16 + 4 = 468

### Binary and Octal
Group bits in threes starting from right, convert to octal numbers.

#### Example:
Binary = 1011010111

| 1   | 011 |  010 | 111 |
| --- | --- | --- | --- |
| 1    | 3     | 2     | 7     |

Octal = 1327

For Octal to binary, it is the same in reverse.

### Binary and Hexadecimal
Group bits in fours starting from right, convert to hexadecimal digits

#### Example
Binary = 1010111011

| 10  | 1011 | 1011 |
| --- | ---- | ---- |
| 2    |B      |B      |

Hexadecimal = 2BB

For Hexadecimal to binary, it is the same in reverse.

### Octal and Hexadecimal
##### Octal to Hexadecimal
Follow the process:
Octal -> Binary -> Hexadecimal

##### Hexadecimal to Octal
Follow the process:
Hexadecimal -> Binary -> Octal

## Approximating Big Powers of 2

| Binary    | Exact Value | Approx. Value | Equivalent |
| --------- | ----------- | ------------- | ---------- |
| 2$^1$$^0$ | 1024        | 1000          | 10$^3$     |
| 2$^2$$^0$ | 1048576     |             1000000  |   10$^6$         |
| 2$^3$$^0$ |10737411824             |         1000000000      |10$^9$            |
| 2$^4$$^0$ |           1099511628000  |      1000000000000         |10$^1$$^2$            |

## Overflow
- When the **number of bits** calculated **exceeds** the storable **range**.
- In a given type of computer, the size of integers is a fixed number of bits (generally 32 or 64 bits). 
- **Overflow** is the term for on operation whose results *exceed the allocated space*

## Negative numbers
- In 8-bit arithmetic, 255 + 1 becomes 0 and acts like -1
### Finding the 2's complement
1. Flip all the bits to the opposite value
2. Add 1 to the new binary value

The new range for signed integers is now -2$^n$$^-$$^1$ to 2$^n$$^-$$^1$ - 1
