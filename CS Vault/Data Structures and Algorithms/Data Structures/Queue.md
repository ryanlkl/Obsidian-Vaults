# What is a Queue?
A **Queue** is another data structure designed to process temporary data. It is similar to stack in many ways, however, it processes data in a different order.

A queue can be described like a line of people at the move theater and the first in the line is the first to carry on. This is *first in, first out* (FIFO).

Queues have **three restrictions**:
- Data can be inserted only at the *end* of a queue
- Data can only be deleted from the *start* of the queue
- Only the first element of that queue can be read

## Queue Implementation
```Python
class Queue:
	def __init__(self):
		self.data = []
		
	def enqueue(self,element):
		self.data.append(element)

	def dequeue(self):
		self.data.pop(0)

	def read(self):
		return self.data[0]
```
