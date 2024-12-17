``` Python3
class HashTable:
	def __init__(self,size=7):
		self.data_map = [None] * size

	def __hash(self,key):
		my_hash = 0
		for letter in key:
			my_hash = (my_hash + ord(letter) * 23) % len(self.data_map)
		return my_hash

	def set_item(self,key,value):
		hash = self.__hash(key)
		if self.data_map[hash] == None:
			self.data_map[hash] = []
		self.data_map[hash].append([key,value])

	def get_item(self,key):
		index = self.__hash(key)
		array = self.data_map[index]
		if self.data_map[index] == None:
			return None
		for i in range(len(array)):
			if array[i][0] == key:
				return array[i][1]
		return None

	def keys(self):
		all_keys = []
		for i in range(len(self.data_map)):
			if self.data[map][i]:
				for j in range(len(self.data_map[i])):
					all_keys.append(self.data_map[i][j][0])
		return all_keys
```