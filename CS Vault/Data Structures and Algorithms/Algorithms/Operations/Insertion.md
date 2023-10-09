# What is Insertion?
**Insertion** puts a value into the array. The efficiency of this operation depends on where the value is inserted into the array.

If we only want to add it to the **end** of the array. This only takes **one** step.

![[Pasted image 20230930172125.png]]

## What's the problem?
Say we want to add the value into the middle of the array. We first need to move all the elements in the array that are currently after the index the insertion will occur. Each move takes another step before the value is added to the array.

![[Pasted image 20231001154617.png]]

![[Pasted image 20231001154648.png]]

![[Pasted image 20231001154707.png]]

![[Pasted image 20231001154720.png]]

![[Pasted image 20231001154733.png]]

