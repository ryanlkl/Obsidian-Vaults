# Breadth First Search (BFS)
``` Python
def bfs(self):
	curr = self.root
	queue = []
	results = []
	queue.append(curr)
	while len(queue) > 0:
		curr = queue.pop(0)
		results.append(curr.value)
		if curr.left:
			queue.append(curr.left)
		if curr.right:
			queue.append(curr.right)
	return results
```

# Depth First Search (DFS)
## Pre Order
``` Python
def dfs_pre_order(self):
	results = []

	def traverse(curr):
		results.append(curr.value)
		if curr.left:
			traverse(curr.left)
		if curr.right:
			traverse(curr.right)
	traverse(self.root)
	return results
```

## Post Order
``` Python
def dfs_post_order(self):
	results = []

	def traverse(curr):
		if curr.left:
			traverse(curr.left)
		if curr.right:
			traverse(curr.right)
		results.append(curr.value)

	traverse(self.root)
	return results
```

## In Order
``` Python
def dfs_in_order(self):
	results = []

	def traverse(curr):
		if curr.left:
			traverse(curr.left)
		results.append(curr.value)
		if curr.right:
			traverse(curr.right)
	traverse(self.root)
	return results
```