Dynamic programming helps to identify the **most common** speed traps in recursive code and how to express these algorithms in term of Big O.

### Unnecessary Recursive Calls
``` Python
def max(array):
	# Base Case
	return array[0] if len(array) == 1

	if array[0] > max(array[1:len(array)-1]):
		return array[0]
	else:
		return max(array[1:len(array)-1])
```

do this:
``` Python
def max(array):
	return array[0] if len(array) == 1

	maxRemainder = max(array[1:len(array)-1])
	if array[0] > maxRemainder:
		return array[0]
	else:
		return maxRemainder
```

# Dynamic Programming through Memoization
**Dynamic programming is the process of optimizing recursive problems that have overlapping subproblems**.

**Memoization** is a technique for reducing recursive calls in cases of overlapping subproblems. This is done by *remembering* previously computed functions. The results are stored in a hash table that will remember the answers.

This hash table is passed as a **second parameter** into the recursive function.
### Implementing Memoization
First, alter the function:
``` Python
def fib(n,memo={}):
	if n == 0 or n == 1:
		return n
	if no memo.get(n):
		memo[n] = fib(n-2,memo) + fib(n-1,memo)
	return memo[n]
```
# Dynamic Programming through Going Bottom Up
This completely **eliminates recursion** and use other approaches.
Same example for fibonacci's sequence:
``` Python
def fib(n):
	if n == 0:
		return 0
	a = 0
	b = 1
	for i in range(1,n):
		temp = a
		a = b
		b = temp + a
	return b
```
