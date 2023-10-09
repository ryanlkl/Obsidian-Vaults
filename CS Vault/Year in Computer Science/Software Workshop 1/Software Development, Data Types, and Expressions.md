# Fundamentals of Python: Chapter 2
## Learning Objectives
`ris:StarS` Describe the basic phases of software development: analysis, design, coding, and testing
`ris:StarS` Use strings for the terminal input and output of text
`ris:StarS` Use integers and floating point numbers in arithmetic operations
`ris:StarS` Construct arithmetic expression
`ris:StarS` Initialise and use variables with appropriate names
`ris:StarS` Import functions from library modules
`ris:StarS` Call functions with arguments and use returned values appropriately
`ris:StarS` Construct a simple Python program that performs inputs, calculations, and outputs
`ris:StarS` Use docstrings to document Python programs
***
## Software Development Process
Process of **planning** and **organising** a program. An example of this is the **[[Introduction to Software Engineering#Waterfall Model|Waterfall Model]]**.
Modern software development is usually **incremental** and **iterative**
	- Analysis and design may produce a **prototype** of a system for coding
Programs rarely work as hoped the first time they are run:
	- You must perform **extensive and careful testing**
	- The cost of developing software is **not spread equally over the phases**

![[Pasted image 20230928183339.png|500]]

## Strings, Assignment, and Comments
E-mail, text messaging, Web Pages, and word processing all ***rely on and manipulate data*** consisting of strings of characters

### Data Types
- **Data types** consists of a set of values and operations that can be performed on them
- **Literal** is the way a value appears to the programmer
- **Int** and **Float** are numerical data types

#### String Literals
**String literals** are **sequences of characters** enclosed in single or double quotation marks

```python
"This is a string"

'This is also a string'
```

**Triple quotation marks** are used for **multi-line paragraphs**:

```python
"""This very long sentence extends
all the way to the next line"""

'''This very long sentence also extends
all the way to the next line'''
```

| Escape Sequence |        Meaning        |
| --------------- |:---------------------:|
| \b              |       Backspace       |
| \n              |        Newline        |
| \t              |    Horizontal tab     |
| \\              |    The \ character    |
| \’              | Single quotation mark |
| \”              | Double quotation mark |

You can also **use concatenation** to join 2 string using "+"

```python
"Hi " + "there," + " Ken!"

=> "Hi there, Ken!"
```

#### Variables and Assignment Statement
Variables associates a name with a value
- Reserved words cannot be used
- Name must **begin with letter or underscore**
- Name can **contain any letter, digit or underscore**
- Names are **case sensitive**

**All uppercase letters** are used as **symbolic constants**

```python
# An example of a symbolic constant:
# Initialise a variable using "="
HELLO = "hello"
```

Variables have 2 purposes:
1. Help the programmer track data change over time
2. Allow programmer to refer to a complex piece of information with simple name (abstraction)

#### Comments and Docstrings
##### Comments
Piece of text that the computer ignores but provides useful information for programmers
##### Docstring
Multi-line string of the form
For example:

```python
“““

Program: circle.py

Author: Ken Lambert

Last date modified: 10/10/17

The purpose of this program is to compute the area of a circle. The input is an integer or floating-point number representing the radius of the circle. The output is a floating-point number labeled as the area of the circle.

”””
```

#### Numerical Data Types and Character Sets
##### Integers
In real life, the range of integers is infinite. A computer's memory places a limit on the magnitude of the largest positive and negative integers.

In python, this is -2^31 to 2^31 - 1.

##### Floating-Point Numbers
Real numbers have infinite precision however python uses floating-point numbers to represent real numbers.
These typically range between -10^308 and 10^308 where the typical precision is 16 digits. It uses "e" to denote x10

##### Character Sets
Character literals look like string literals and are of string type. They belong in several different **character sets** like **ASCII** and **Unicode**.

**ord** and **chr** functions convert characters to and from ASCII respectively.

##### Expressions
- A literal **evaluates to itself**
- A variable reference **evaluates to the variables current value**
- **Expressions** provide easy ways to perform operations on data values to produce other values
- When each operand is of a **different data type**, the resulting values is of the more general type

#### Mixed-Mode Arithmetic and Type Conversions
**Mixed-mode arithmetic** involves integers and floating-point numbers

```python
>>> 3.14*3*2
>>> 28.26
```

You must use a **type conversion function** when working with input of numbers
- It is a function with the same name as the data type to which it converts
Input function returns a string as its value
- You must use the **int** or **float** function to convert the string to a number before performing arithmetic
- Python is a **strongly typed** programming language

#### Using Functions and Modules
Python includes many useful functions, which are organised in libraries of code called modules
##### Calling Functions: Arguments and Return Values
A **function** is a chunk of code that can be called by name to perform a task. They often require **arguments** or **parameters** and can be either **optional** or **required**.
When a function completes its task, it may **return a value back** to the part of the program that called it

##### The Math Module
The math module **includes functions that perform basic mathematical operations**.

Importing module:

```python
from math import pi, sqrt # Imports specific resources (pi and sqrt)
# or use
from math import * # Imports all resources from the module
```

### Program Format and Structure
Start with comment with author's name, purpose of program, and other relevant information **in a docstring**.

Then include statements like:
- Module imports needed
- Initialise important variables with appropriate comments
- Prompt user for input data and save input data in variables
- Process inputs to produce the results
- Display results

### Running a Script from a Terminal Command Prompt
1. Open a terminal command prompt window
2. Navigate or change directories until the prompt shows directory that contains the script
3. Run the script by entering the command:

```python
>>> python3 scriptName.py
```

