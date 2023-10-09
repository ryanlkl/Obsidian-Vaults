# Binary Arithmetic
## 2's Complement
In **2's complement**, the convention is the start all **positive numbers with 0** and all *negative numbers with 1*.

# How are Real Numbers Represented?
There are 2 methods:
- **Fixed Point**: The binary point is fixed
- **Floating Point**: The binary point floats to the right of the most significant 1 and an exponent is used

## Fixed Point Decimal to Binary
| Number | Number Doubled | Value |
| ------ | -------------- | ----- |
| 0.537  | **1**.074      | **1** |
| 0.074  | **0**.148      | **0** |
| 0.148  | **0**.296      | **0** |
| 0.296  | **1**.592     | **1** |
| 0.592  | **0**.184      | **0** |
| 0.184       |**0**.368                |**0**       |

0.537$_1$$_0$ = 0.1001$_2$ 
## Fixed Point Binary to Decimal
Do the same as binary to decimal but include the negative powers for binary values < 0

| 2$^3$ | 2$^2$ | 2$^1$ | 2$^0$ | 2$^-$$^1$ | 2$^-$$^2$ | 2$^-$$^3$ | 2$^-$$^4$ |
| ----- | ----- | ----- | ----- | --------- | --------- | --------- | --------- |
| 1     | 1     | 0     | 1     | 0         | 1         | 0         | 1         |
| 8      |4       |0       |1       |0           |0.25           |0           |0.0625           |

1101.0101 $_2$ = 13.3125 $_1$$_0$

## Floating Point Representation for Fractions
Numbers represented as: *+/- m x 2$^e$*

 | Sign | Mantissa | Exponent |
 | ---- | -------- | -------- |
 |0 for positive and 1 for negative      |Actual Significant Digits          |  "Signed" binary showes where binary point goes        |

### Examples:
42.625 = 101010.101 = 1.01010101 x 2 $^5$

| Sign | Mantissa | Exponent |
| ---- | -------- | -------- |
| 0 as it is positive     |5 + 127 where 5 is the power of the exponent so 1000 0100         |010 1010 1000 0000 0000 0000          |

## Numerical Precision
Fixed point is convenient and intuitive but has **2 problems**:
1. **Numerical Precision**: Only values that are an integer multiple of the smallest power of two can be represented exactly
2. **Numerical Range**: Increased precision of non-integer part is at the expense of the numerical range