# What is a Linked List?
**Linked lists** are data structures that represent a list of items. Unlike an array, the data can be **scattered across different cells** throughout the computer's memory. Each connected data is referred to as a **node**.

![[Pasted image 20231010142854.png]]

Initialising:
``` Python
class ListNode():
	def __init__(self, value=0, next=None):
		self.value = value
		self.next = next
```

## Reading from a Linked List
If you want to read an item in an linked list, you cannot immediately jump to that element. Only the element before knows where the next element is stored.

To read from the third node, then the first node must be read to find the second to find the third.

As the linked list requires you to traverse it to read a value, this is **O(n)** time complexity.
``` Python
def read(index):
	curr = head
	curr_index = 0
	while curr and curr_index < index:
		curr = curr.next
		curr_index += 1
	return curr if curr else None
```

## Searching from a Linked List
``` Python
def index_of(value):
	curr = head
	index = 0
	while curr:
		if curr.val == value:
			return index
		curr = curr.next
		index += 1
	return None
```

## Insertion in a Linked List
To insert a value, we need to change the *next* link from the node to the left of where we want to insert the node.

![[Pasted image 20231010144834.png]]
``` Python
def insert(index,value):
	newNode = Node(value)
	if index == 0:
		newNode.next = head
		return newNode
	curr = head
	curr_index = 0
	while curr_index < index - 1:
		curr = curr.next
		curr_index += 1
	newNode.next = curr.next
	curr.next = newNode
```
## Deletion in a Linked List
To delete an item from the linked list, we need to change the next value of the node before to the node after the current.
``` Python
def delete(index):
	if index == 0:
		head = head.next
	curr = head
	curr_index = 0
	while curr_index < index - 1:
		curr = curr.next
		curr_index += 1
	temp = curr.next.next
	curr.next = temp
```
# Doubly Linked List