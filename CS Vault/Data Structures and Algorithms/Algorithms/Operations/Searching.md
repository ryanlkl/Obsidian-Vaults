# What is Searching?
**Searching** means to look to see whether a particular value exists within an array and at which index it is found.

Because you do not know the index when searching therefore the computer *cannot* jump to any particular value. So the computer can only see the following:

![[Pasted image 20230930170500.png]]

To actually search for the value in the array, the computer must **go through each element** and **check whether or not the current element is the value we are looking for**.

### Example:

In the array above, we are trying to look for the value "dates". To do this we have to do the following:
1. Go to the first element
2. Check whether the value is "dates"
3. If it is not, we go to the next element and repeat from **step 2**
4. If it is, we save the index the value is stored.
##### Step 1:

![[Pasted image 20230930170749.png]]

"Apples" is not "dates" so we move on to the next index.
##### Step 2:

![[Pasted image 20230930171644.png]]

"bananas" is not "dates" so we move on to the next index.
##### Step 3:

![[Pasted image 20230930171751.png]]

"cucumbers" is not "dates" so we move on to the next index.
##### Step 4:

![[Pasted image 20230930171828.png]]

"dates" is "dates" so the value is in the array and the index the value lies in is **index 3**.

