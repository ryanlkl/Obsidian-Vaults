Quicksort relies on **partitioning**.
## Partitioning
**Partitioning** is taking a random value from the array (the *pivot*) and make sure all numbers less than the pivot is on the left and all numbers greater are on the right.
### Example
![[Pasted image 20231008200200.png]]

Select the rightmost element to be the pivot and set pointers to the start and end of the subsequence on the left.

![[Pasted image 20231008200306.png]]

Follow these steps:
1. Move the **left pointer** continuously right until it reaches a value greater than or equal to the pivot
2. Move the **right pointer** continuously left until it reaches a value less than or equal to the pivot
3. If the left pointer is has reached or passed the right, move on to step 4. Otherwise, swap the values and repeat steps 1,2 and 3
4. Swap the pivot with the value that the left pointer is pointing to

##### Example
###### Step 1:
![[Pasted image 20231008200638.png]]

0 is less than the pivot, move right.

![[Pasted image 20231008200719.png]]

5 is greater than the pivot so we stop.
###### Step 2
6 is greater than the pivot, move left.

![[Pasted image 20231008200843.png]]

1 is less than the pivot so we stop
###### Step 3
The left hasn't reached the right so we swap the values and continue.

![[Pasted image 20231008200947.png]]

###### Step 1
Move the left pointer.

![[Pasted image 20231008201023.png]]

2 is less than the pivot so continue.

![[Pasted image 20231008201059.png]]

5 is greater than the pivot so we stop. Our left pointer has also met the right pointer.
###### Step 4
Swap the pivot and the value

![[Pasted image 20231008201203.png]]

The array isn't completely sorted but the partition was completed
#### Code
``` Python
class SortableArray:
	def __init__(self,array):
		self.array = array

	def partition(l,r):
		pivot_index = r
		pivot = self.array[pivot_index]
		r -= 1
		while True
			while self.array[l] < pivot:
				l += 1

			while self.array[r] > pivot:
				r -= 1

			if l >= r:
				break
			else:
				self.array[l],self.array[r] = self.array[r],self.array[l]
				l += 1


		array[l],array[pivot_index] = array[pivot_index],array[l]
		return l
```
# Quick Sort
**Quick sort** is a combination of [[Recursion|recursion]] and partitions:
1. Partition the array, this moves the pivot to the correct location
2. Treat the left and right sections as subarrays and use recursion
3. When the subarray's length is 1 or 0 is when the recursion reaches its base case

![[Pasted image 20231008202036.png]]

![[Pasted image 20231008202056.png]]

### Code
``` Python
class SortableArray():
	def __init__(self,array):
		self.array = array

	def partition(l,r):
		pivot_index = r
		pivot = self.array[pivot_index]
		r -= 1
		while True
			while self.array[l] < pivot:
				l += 1

			while self.array[r] > pivot:
				r -= 1

			if l >= r:
				break
			else:
				self.array[l],self.array[r] = self.array[r],self.array[l]
				l += 1


		array[l],array[pivot_index] = array[pivot_index],array[l]
		return l

	def quicksort(l,r):
		if r - l <= 0:
			return

		pivot_index = self.partition(l,r)
		self.quicksort(l,pivot_index-1)
		self.quicksort(pivot_index+1,r
```

Time complexity: O(NlogN)
