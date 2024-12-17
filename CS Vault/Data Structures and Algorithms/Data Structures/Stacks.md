# What is a Stack?
**Stacks** store data in the same way [[Ordered Arrays]] and Arrays do. It is a simple list of elements but has 3 constraints:
1. Data can be inserted only at the end of a stack
2. Data can be deleted only from the end of a stack
3. Only the last element of a stack can be read

![[Pasted image 20231002195650.png]]

It follows the LIFO protocol. This stands for *Last in, First out* as the *last* value put into the stack is the *first* out.
## Abstract Data Types
Most programming languages don't come with a built-in stack data type or class. To initialise it, do the following:

```Python
class Stack():
	def __init__(self):
		self.stack = []

	def push(self,element):
		self.stack.append(element)

	def pop(self):
		self.stack.pop()

	def read(self):
		return self.stack[-1]
```

Despite not typically be used to store data on a long-term basis, it can be great tool to handle **temporary data** as part of various algorithms.
## Importance of Constrained Data Structures
A stack and [[Interview Prep/Queue/Queue|queue]] is a **constrained** data structure and are important for several reasons.
#### Preventing bugs
When using an array instead of a stack, if a programmer inadvertently writes code the removes items from the middle, the algorithm will break. By using the stack, we're forced to only remove items from the top as it is impossible to access the other data in the stack.
#### Mental Model
The stack can apply the *LIFO* method to solve all sorts of problems such as a JavaScript Linter.
