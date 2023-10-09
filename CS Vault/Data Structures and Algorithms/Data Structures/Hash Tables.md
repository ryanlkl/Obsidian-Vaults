# What are Hash Tables?
**Hash tables** is a **data structure** that allows *fast reading*. Unlike [[Reading]], hash tables contain key, value pairs that allow the computer to jumps straight to a value based on its key.

Hash tables stores its data in a bunch of cells in a row like an array and [[Ordered Arrays|ordered array]]. See below:

![[Pasted image 20231002194615.png]]

## Reading from a Hash Table
Reading from a **hash table** is similar to the operation [[Reading]]. The only difference is that hash tables use "keys" to locate values.

## Making an efficient Hash Table
A hash table's efficiency depends on **3 factors**:
- **How much data** we're storing in the hash table
- **How many cells** are available in the hash table
- **Which hash function** we're using