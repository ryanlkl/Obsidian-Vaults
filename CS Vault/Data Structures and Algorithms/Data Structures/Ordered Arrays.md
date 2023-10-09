# What is an Ordered Array?
An **ordered array** is the same structure as an array. The only difference is that the values are in **order**.
## Insertion in Ordered Arrays.
To insert a new value into the array, we use a similar method to insertions in [[Sets]]. As the values must be in order, we must find the index that is suitable for the new element.

### Example
Say we have the array [3,17,80,202] and we want to insert 75 into the ordered array.
We *cannot* insert it at the end as 75 < 202 and we cannot insert it at the beginning because 75 > 3.

The first step is to find the correct location:

![[Pasted image 20231001201841.png]]

3 is less than 75 so we check the next element.

![[Pasted image 20231001201921.png]]

17 is less than 75 so we check the next element.

![[Pasted image 20231001212540.png]]

80 is greater than 75 so we know that the next element is directly left of 80.

To insert 75 to the left or 80, we first move 80 and all the values on the right along 1.

![[Pasted image 20231001224943.png]]

![[Pasted image 20231001225004.png]]

We can now insert the new value.
![[Pasted image 20231001225023.png]]

## Searching in an Ordered Array
As the array is ordered, there are **2** main methods to search for an element in an **ordered array**. These methods are:
- Linear Search
- Binary Search

### Linear Search
As the name suggests, the method loops linearly through the array and checks whether or not the element is equal to the target.

``` Python
def linearSearch(array, target): # Accepts 2 arguments
	for i in range(len(array)): # Loop through 0 to end of the array
		element = array[i]
		if element == target: # Checks each element to the target
			return index
		elif element > target: # Target is not in the array
			break
	return None
```

This loops through each element until it reaches the target. At that point, the index is returned; however, if the target is not in the array and the element is bigger than the target, the loop breaks and **None** is returned. 

### Binary Search
Binary search is a much more efficient method of finding elements in an ordered array. The algorithm checks the middle value of the array, checking whether the element is bigger than, less than or equal to the target.
- If the target is bigger, then the algorithm checks the second half using the same method.
- If the target is smaller, then the algorithm checks the first half using the same method.
- When the value is found then the index is outputted

``` Python
def binarySearch(array, target):
	i,j = 0, len(array) - 1 # Sets the start and end of the subarray
	while i <= j: # Loop condition
		middle = (i + j)//2 # Finds the middle index of the subarray
		if array[middle] > target: 
			j = mid - 1 # Makes subarray the first half
		elif array[middle] < target:
			i = mid + 1 # Makes subarray the second half
		else:
			return middle # Middle Element is the target
	return None
```