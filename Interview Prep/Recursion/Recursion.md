# Binary Search Tree
``` Python3
def __r_contains(self,current_node,value):
	if not current_node:
		return False
	if value == current_node.value:
		return True
	if value < current_node.value:
		return self.__r_contains(current_node.left,value)
	if value > current_node.value:
		return self.__r_contains(current_node.right,value)

def r_contains(self,value):
	return self.__r_contains(self.root,value)

def __r_insert(self,current_node,value):
	if current_node == None:
		return Node(value)
	if value < current_node.value:
		current_node.left = self.__r_insert(current_node.left,value)
	if value > current_node.value:
		current_node.right = self.__r_insert(current_node.right,value)
	return current_node

def r_insert(self,value):
	self.__r_insert(self.root,value)

def min_value(self,curr_node):
	while curr_node.left:
		curr_node = curr_node.left
	return curr_node.value

def __delete_node(self,curr_node,value):
	if not curr_node:
		return None
	if value < curr_node.value:
		curr_node.left = self.__delete_node(curr_node.left,value)
	elif value > curr_node.value:
		curr_node.right = self.__delete_node(curr_node.right,value)
	else:
		if not curr_node.left and not curr_node.right:
			return None
		elif not curr_node.left:
			curr_node = curr_node.right
		elif not curr_node.right:
			curr_node = curr_node.left
		else:
			sub_tree_min = self.min_value(curr_node.right)
			curr_node.value = sub_tree_min
			curr_node.right = self.__delete_node(current_node.right, sub_tree_min)
	return curr_node

def delete_node(self,value):
	self.__delete_node(self.root,value)
```