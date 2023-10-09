				# What is Recursion?
**Recursion** is a key concept that can be used to solve certain types of tricky problems
Recursion occurs when the function reoccurs inside the function. An example of this is the factorial function:

``` Python
def factorial(num):
	if num == 1:
		return 1
	return num * factorial(num-1)
```

To write a recursive function, you require a **base case** to terminate the repetition to allow the function to return. Recursion uses a **call stack** that acts like a regular [[Stacks|stack]] where the last value in is the first out (LIFO).

## Top-Down Thought Process
When doing the **top-down thought process** there are 3 factors:
1. Imagine the function you're writing has already been implemented by someone else
2. Identify the subproblem of the problem
3. See what happens when you call the function on the subproblem and go from there

### Examples
##### Sum of an Array
``` Python
def sum(array):
	if len(array) == 1:
		return array[0]
	return array[0] + sum(array[1:len(array)-1])
```
##### Reverse a String
``` Python
def reverse(string):
	if len(string) == 1:
		return string[0]
	return reverse(string[1:len(string)]) + string[0]
```
##### Counting X
This returns all the "x"'s in a given string.
``` Python
def count_x(string):
	if string[0] == "x":
		return 1 + count_x(string[1:len(string)-1])
	else:
		return count_x(string[1:len(string)-1])
```
##### The Staircase Problem
Let's say we have a staircase of N steps, and a person has the ability to climb one, two, or three steps at a time. How many different possible "paths"  can someone take to reach the top?

![[Pasted image 20231007123119.png]]

We can determine the number of paths(n) = number_of_paths(n-1) + number_of_paths(n-2) + number_of_paths(n-3) as the person could take 3 steps from n-3 stairs or 2 steps from n-2 stairs or 1 step from n-1.

``` Python
def number_of_steps(n):
	return 0 if n < 0:
	return 1 if n == 1 or n == 0
	return number_of_paths(n-1) + number_of_paths(n-2) + number_of_paths(n-3)
```

This is also fibonacci's sequence
