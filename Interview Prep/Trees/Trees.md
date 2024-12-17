``` Python3
class Node:
	def __init__(self,value):
		self.value = value
		self.right = None
		self.left = None

class BinarySearchTree:
	def __init__(self):
		self.root = None

	def insert(self,value):
		new_node = Node(value)
		if not self.root:
			self.root = new_node
			return True
		curr = self.root
		while True:
			if new_node.value == curr.value:
				return False
			if new_node.value > curr.value:
				if curr.right is None:
					curr.right = new_node
					return True
				curr = curr.right
			else:
				if curr.left is None:
					curr.left = new_node
					return True
				curr = curr.left
			
	def contains(self,value):
		if not self.root:
			return False
		curr = self.root
		while curr:
			if curr.value == value:
				return True
			if curr.value > value:
				curr = curr.left
			else:
				curr = curr.right
		return False
		
```