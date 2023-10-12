---
Module: Computer Systems
Date: 09-10-2023
Topic: "Algorithm Design and Analysis: Efficiency and Complexity"
---
**Overview**:
- Motivation
- Efficiency: Space Complexity
- Efficiency: Time Complexity
	- Algorithms
	- Problems
### Efficiency Checklist
- [ ] Is our implementation of our algorithm or data representation efficient?
- [ ] Could we improve our code to make it run faster?
- [ ] Could we improve our data representation so it uses less memory?#
- [ ] What is the trend when length of data increases?
- [ ] What is the trend when the size of the problem grows?
## Complexity
These **complexities** require [[Big O Notation]].
### Space Complexity
Usually space complexity is not considered in the same way as computational complexity:
- Memory and bandwidth are limited by practical constraints
- We can add memory to cope with a bigger problem
- We can constrain our problem to the practical constraints:
	- We restrict the resolution of videos to what is practical
	- We restrict the resolution of 3D models to what is practical
	- We can use other techniques to reduce the memory demands
##### Example: Videos
The typical HD video:
- 1920x1080 pixels (4 bytes per pixel)
	- approx. 2 MPixels, approx. 8MBytes
- 25 fps
	- 200 MBytes/sec
###### Solution:
- Compression (up to 200:L1)
	- Using empirical knowledge of human vision and video streams
	- Lossy compression (cf. lossless compression)
- Reduce frame rate or resolution
- Constrained by practical constraints

##### 2D and 3D images#
When we double the resolution of a 2D image, the number of pixels changes from n to n$^2$.
When we double the resolution of a 3D image, the number of pixels changes from n to n$^3$.

### Time Complexity
#### Algorithm Efficiency
- **Resource usage** of an algorithm:
	- *time* (runtime) and *space* (computer memory)
	- network usage, hardware requirements
##### Empirical Analysis
**Idea:** implement the algorithm and time it
	- Manually: Using stopwatch
	- Automatically: Using timer function

**Time complexity** is the *number of operations* that an algorithm requires to execute, in terms of the *size* of the input or problem
###### Example 1
Look up a value *v* in an array *x* of integers
[1,4,17,3,90,79,4,6,81]
**Algorithm:** Linear Search
Input: array *x* of size *n*, integer *v*
Return: Index of first occurrence of *v* in *x*, or -1 if none.
**Time complexity**: O(n)

``` Python
def linearSearch(array,target):
	for i,num in enumerate(array):
		if num == target:
			return i
	return -1
```
###### Example 2
Matrix-Vector Multiplication: x = Ab
	*n x n* matrix *A*, vector *b* of size *n*
``` Python
def matrixVectorMultiplication(matrix,vector):
x = [0] * (len(nums)-1)
	for i in range(len(nums)-1):
		for j in range(len(nums)-1):
			x[i] = x[i] + A[i][j] * b[j]*
```

#### Complexity Classes
- O(1) = "**Constant**"
- O(n) = "**Linear**"
- O(log n) = "**Logarithmic**"
- O(n log n) = "**Log Linear**"
- O(n$^2$) = "**Quadratic**"
- O(n$^3$) = "**Cubic**"
- O(2$^n$) = "**Exponential**"
![[Pasted image 20231010001729.png]]

![[Pasted image 20231010001752.png]]

### Algorithms vs Problems
#### Algorithm Complexity
- Worst-case run time of algorithm
- Most informative complexity
#### Problem Complexity
- Complexity class = set of problems
- Problem X is in complexity class O(f(n)) if there exists an algorithm to solve it in O(f(n))