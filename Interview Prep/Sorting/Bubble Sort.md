Continuously bubble up the largest value to the end until the list is sorted

``` Python
def bubble_sort(arr):
	for i in range(len(arr) - 1,0,-1): # Loop backwards through array
		for j in range(i):
			if arr[j] > arr[j+1]:
				temp = arr[j]
				arr[j] = arr[j+1]
				arr[j+1] = temp
	return arr
```