# What are Sets?
Sets are a **data structure** that do not allow duplicate values to be contained within it. An **array-based** set is just like an array: a simple list of values. The only difference is that it doesn't contain duplicates.
## Insertion in Sets
Unlike [[Insertion]] in arrays.  As sets **don't add duplicates**, the computer must first check all the elements in the current array to see if the new element **already exists**. If the set *doesn't contain the new element*, then the computer will add the new element.

### Example
Add "figs" to the set.

First check whether "figs" is already in the set.

![[Pasted image 20231001191611.png]]

"Figs" isn't at index 0. Check the next element.

![[Pasted image 20231001191905.png]]

"Figs" isn't at index 1. Check the next element.

![[Pasted image 20231001192034.png]]

"Figs" isn't at index 2. Check the next element.

![[Pasted image 20231001192121.png]]

"Figs" isn't at index 3. Check the next element.

![[Pasted image 20231001192200.png]]

Now that we've searched the entire set, we know that "figs" isn't in the set. We now insert figs at the end of the set. This method is the same method used in [[Insertion]].