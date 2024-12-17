``` python3
def Node:
	def __init__(self,value):
		self.value = value
		self.next = None

def Queue:
	def __init__(self,value):
		new_node = Node(value)
		self.first = new_node
		self.last = new_node
		self.length = 1

	def enqueue(self,value):
		new_node = Node(value)
		if self.first is None:
			self.first = new_node
			self.last = new_node
		else:
			self.last.next = new_node
			self.last = new_node
		self.length += 1

	def dequeue(self,value):
		if self.length == 0:
			return None
		temp = self.first
		if self.length == 1:
			self.first = None
			self.last = None
		else:
			self.first = self.first.next
			temp.next = None
		self.length -= 1
		return temp
```