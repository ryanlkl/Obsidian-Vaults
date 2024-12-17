finds the smallest index, swap with the first
move to the next index, and repeat
``` Python
def selection_sort(arr):
	for i in range(len(arr) - 1):
		min_index = i
		for j in range(i+1,len(arr)):
			if arr[j] < arr[min_index]:
				min_index = j
		if min_index != i:
			temp = arr[i]
			arr[i] = arr[min_index]
			arr[min_index] = j
	return arr
```