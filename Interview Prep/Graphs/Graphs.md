![[Pasted image 20241012134918.png]]
![[Pasted image 20241012135018.png]]

``` Python3
class Graph:
	def __init__(self):
		self.adj_list = {}

	def add_vertex(self,vertex):
		if vertex not in self.adj_list.keys():
			self.adj_list[vertex] = []
			return True
		return False

	def add_edge(self,v1,v2):
		if v1 in self.adj_list.keys() and v2 in self.adj_list.keys():
			self.adj_list[v1].append(v2)
			self.adj_list[v2].append(v1)
			return True
		return False

	def remove_edge(self,v1,v2):
		if v1 in self.adj_list.keys() and v2 in self.adj_list.keys():
			self.adj_list[v1].remove(v2)
			self.adj_list[v2].remove(v1)
			return True
		return False

	def remove_vertex(selv,vertex):
		if vertex not in self.adj_list.keys():
			return False
		for key in self.adj_list[vertex]:
			self.adj_list[key].remove(vertex)
		del self.adj_list[vertex]
		return True

		
```