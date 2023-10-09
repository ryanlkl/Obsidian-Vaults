## Learning objectives
`fas:Star` Write a loop to repeat a sequence of actions a fixed number of times
`fas:Star` Write a loop to traverse the sequence of characters in a string
`fas:Star` Write a loop that counts down and a loop that counts up
`fas:Star` Write an entry-controlled loop that halts when a condition becomes false
`fas:Star` Use selection statements to make choices in a program
`fas:Star` Construct appropriate conditions for condition-controlled loops and selection statements
`fas:Star` Use logical operators to construct compound Boolean expressions
`fas:Star` Use a selection Statement and a break statement to exit a loop that is not entry controlled
# Loops and Selection Statements
## For Loops
Each repetition of a loop is known as a **pass** or **iteration**.
There are 2 types of loops:
1. **Definite Iteration**: Repeats an action a predefined number of times
2. **Indefinite Iteration**: Repeats an action until a condition is met

### Executing a Statement a Given Number of Times
The first line of code in a loop is often called the **loop header**. This defines whether the loop is **definitely** or **indefinitely**.
The rest is the **loop body** which determines the actions taken during the loop.

##### Example

```Python
for eachPass in range(4): # This is the loop header
	print("It's alive!", end="") # This is the loop body

# The format of a for loop is:
for <variable> in range(<integer expression>):
	<statement 1>
	...
	...
	<statement n>
```

The function **range()**, when only **one** input is entered, loops through 0 to 3 excluding the 4. 

When **two** inputs are entered, the function will loop through from the *first argument inclusively* to the *second argument exclusively*.

When **three** inputs are entered, the function will loop through from the *first argument inclusively* to the *second argument exclusively* in *in steps of the third argument*.
##### Example
Compute 2$^3$ = 2 x 2 x 2

``` Python
number = 2 # Initialise the variable "number" to be 2
exponent = 3 # Initialise the variable "exponent" to be 3
product = 1 # Initialise the variable "product" to be 1

# Loop header to repeat the exponent number of times
for eachPass in range(exponent):
# Every pass multiplies the current product value by the number variable and stores it
	product *= number
	# Output the product variable
	print(product, end="") 
```

The variable **"product"** acts as a multiplication **accumulator** during the program. If this were set to 0, the program would continuously output 0 as anything multiplied by 0 equals 0.

### Traversing Contents of a Data Sequence

``` Python
# The format to traverse a data sequence is as follows:
for <variable> in <data sequence>:
	<statement 1>
	...
	...
	<statement n>
```

### Formatting Text for Output
``` Python
# This is normally written in the format:
%<field width>s % <datum>
```
The **"s"** represents **"string"**. **"f"** and **"d"** represent **floating-point** and **denary** respectively.

Here is an example:
We want 3.14 to be a width of 6 and a precision of 3 for a float:
``` Python
salary = 3.14
print("%6.3f" % salary) # This outputs 3.140
```

## Selection
### *if* and *if-else* statements
#### Boolean Type, Comparisons, and Boolean Expressions

| Comparison Operator | Meaning                  |
| ------------------- | ------------------------ |
| ==                  | Is equal to              |
| !=                  | Is not equal to          |
| <                   | Is less than             |
| >                   | Is greater than          |
| <=                  | Is less than or equal to |
| >=                    |Is greater than or equal to                          |

Using these outputs **True** or *False*.

#### If-Else Statements

![[Pasted image 20231001145813.png]]

#### One-way Selection Statements

![[Pasted image 20231001145904.png]]

#### Multi-way if statements

``` Python
if <condition 1>:
	<action 1>
elif <condition 2>:
	<action 2>
...
...
elif <condition n>:
	<action n>
else:
	<final action>
```

![[Pasted image 20231001150033.png]]

#### Logical Operators and Compound Boolean Expressions
These expressions are **and**, **or** and **not**

![[Pasted image 20231001150152.png]]

## Conditional Iteration: The *While* Loop
This loop will continue to operate until a condition is met.

``` Python
while <condition>:
	<action>
```

![[Pasted image 20231001150333.png]]

### Break Statement
The **break** statement will terminate the loop it is in. This is generally put into a condition that must be passed to break the loop.