Always start with second item in list
``` Python
def insertion_sort(arr):
	for i in range(1,len(arr)):
		temp = arr[i]
		j = i - 1
		while temp < arr[j] and j >= 0:
			arr[j+1] = arr[j]
			arr[j] = temp
			j -= 1
	return arr
```