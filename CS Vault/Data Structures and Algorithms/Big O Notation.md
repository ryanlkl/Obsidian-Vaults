# What is Big O Notation?
**Big O notation** is the measurement used to describe the efficiency of algorithm.

People use different processors with different specs so the runtime of a code will vary on different devices. Big O notation allows you to **describe generally** how efficiently a program function depending on the **steps required**.

The value between the brackets describe the **proportionality** of the number of steps against the number of elements inputted into the code.

**O(1)** is described to be the *fastest* kind of algorithm as, no matter how big the input gets, the number of steps required **remains the same**.

![[Pasted image 20231001231100.png]]

Big O Notation is a measure of the **worst case scenario** as this is to longest number of steps required for your algorithm.

[[Ordered Arrays#Binary Search|Binary Search]] is expected to be O(log$_2$n) as the number of steps is **exponentially proportional** to the number of steps that is required for the algorithm.

![[Pasted image 20231001232020.png]]

## Other Algorithms
### Bubble Sort
Bubble sort is a **simple sorting algorithm** that follow these steps:
1. Point to 2 consecutive numbers of an array and compare them.
2. If the 2 numbers are out of order, swap them
3. Repeat this with the next 2 consecutive numbers
4. When you reach the end, repeat steps 1-3 until the array is completely sorted

##### Example
Say we have an array that we need to sort: [4,2,7,1,3]

First check whether the first 2 consecutive elements are in order.

![[Pasted image 20231002113331.png]]

4 is bigger than 2 so we swap them.

![[Pasted image 20231002113400.png]]

check the next 2 consecutive elements, 4 and 7.

![[Pasted image 20231002113439.png]]

They are in the correct order, so move on.

![[Pasted image 20231002113509.png]]

7 is greater than 1 so we swap them.

![[Pasted image 20231002113556.png]]

Check the next 2 consecutive elements, 7 and 3.

![[Pasted image 20231002113635.png]]

7 is greater than 3 so we swap them.

![[Pasted image 20231002113711.png]]

After the first iteration, we now know that the final value is in the correct place, we repeat the previous steps till the number of sorted numbers == the length of the array.

``` Python
def bubbleSort(array):
	unsorted_until_index = len(list) - 1
	sorted = False

	while no sorted:
		sorted = True
		for i in range(unsorted_until_index):
			if list[i] > list[i + 1]:
				list[i], list[i + 1] = list[i + 1],list[i]
				sorted = False
		unsorted_until_index -= 1
	return list
```

##### Efficiency of Bubble Sort
The algorithm contains 2 significant steps:
1. **Comparison**: 2 numbers are compared with one another to determine if it is order
2. **Swaps**: 2 numbers are swapped with one another in order to sort them

Bubble sort is given the notation **O(n$^2$)** as it roughly takes n$^2$ steps for n data elements.

# Optimising Code with and without Big O
Algorithms could be described in the same way however one can still be faster than the other. An example of this is bubble sort and **selection sort**.
### Selection Sort
Selection sort is also **O(n$^2$)**.

The steps required for the sort are:
1. Check each cell of the array from left to right and determine the current lowest value found

![[Pasted image 20231002115437.png]]

2. Swap the smallest value with the value, the previous step began with.

![[Pasted image 20231002115538.png]]

3. Repeat steps 1 and 2 moving along the array

##### Example
Say we want to sort the array [4,2,7,1,3]

We first find what the smallest value is at each point.

![[Pasted image 20231002115727.png]]

![[Pasted image 20231002115801.png]]

![[Pasted image 20231002115829.png]]

![[Pasted image 20231002115907.png]]

![[Pasted image 20231002115927.png]]

1 is the smallest value found, so we swap it with the value we started on:

![[Pasted image 20231002120009.png]]

This is repeated from 2 in [1,2,7,4,3]
The steps are shown below:
[1,2,7,4,3,] as 2 is the smallest in the subarray so there is no swap
[1,2,3,4,7] as 3 is the smallest so it is swapped with 7
[1,2,3,4,7] as 4 is the smallest in the subarray so there is no swap

The entire array is now sorted.

``` Python
def selectionSort(array):
	for i in range(len(array) - 1):
		lowestNumberIndex = i
		for j in range(i + 1, len(array)):
			if array[j] < array[lowestNumberIndex]:
				lowestNumberIndex = j
		if lowestNumberIndex != i:
			array[i],array[lowestNumberIndex] = array[lowestNumberIndex],array[i]
	return array
```

When comparing this to bubble sort, we notice that the number of steps practically halves.

![[Pasted image 20231002120832.png]]

However, when using big o notation, we **ignore the constants** so this is described the same as bubble sort.

# Optimising for Optimistic Scenarios
The worst case scenario isn't the only one that needs to be considered. Being able to consider *all* scenarios is important when choosing the appropriate algorithm for every situation.

### Insertion Sort
The steps required in **insertion sort** are:
1. Temporarily remove the value at index 1 and store it in a temporary variable. This will leave a gap at that index.
2. Compare each value on the left of the temporary variable and shift them to the right if they are larger.
3. Insert the temporary variable in the gap
4. Repeat steps 1 to 3 with the next indexes from 1

##### Example
We want to use **insertion sort** to order the array [4,2,7,1,3]

We start at index 1 and store it in a temporary variable.

![[Pasted image 20231002122926.png]]

Compare the value to the elements on the left.

![[Pasted image 20231002123000.png]]

4 is greater than 2 so we shift it.

![[Pasted image 20231002123318.png]]

We can now insert 2 back into the empty space

![[Pasted image 20231002124449.png]]

We repeat this for index 2.

![[Pasted image 20231002124536.png]]

4 isn't lower so 7 is put back down and index 3 is tried.

![[Pasted image 20231002124615.png]]

7 is bigger than 1 so it is shifted. 4 is bigger than 1 so it is shifted. 2 is bigger than 1 so it is shifted. 1 Is inserted into the empty space.

![[Pasted image 20231002124731.png]]

Index 4 is tried. 7 is bigger than 3, 4 is bigger than 3, 2 isn't so 3 is inserted at index 2.

![[Pasted image 20231002124844.png]]

``` Python
def insertionSort(array):
	for i in range(1,len(array)):
		temp = array[i]
		position = i - 1

		while position >= 0:
			if array[position] > temp:
				array[position + 1] = array[position]
				position -= 1
			else:
				break
		array[position + 1] = temp
	return array
```

##### Efficiency of Insertion Sort
The number of steps required is N$^4$ + N$^3$ + N$^2$ + N
We take the efficiency to be **O(N$^4$)** as it is the most significant. As the number of steps increases, the other values become smaller and smaller.

### Average Case
In the **worst-case scenario**, selection sort is **faster than insertion sort**. The best and worst cases occur relatively infrequently.

![[Pasted image 20231002154418.png]]

![[Pasted image 20231002125802.png]]
