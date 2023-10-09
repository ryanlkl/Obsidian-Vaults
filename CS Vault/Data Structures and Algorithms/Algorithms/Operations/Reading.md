# What is Reading?
**Looking up** what value is contained at a **particular index** inside the array.

The computer can read from the array in just **one step**. This is because computers can **jump to any particular index** in the array and look inside.

The **computer's memory** can be viewed as a giant collection of cells like below:

![[Pasted image 20230930165717.png]]

When a program **declares an array**, a contiguous **set of empty cells** is **allocated**.

![[Pasted image 20230930165833.png]]

**Every cell** in a computer's memory has a **specific address**. 
### Example:

![[Pasted image 20230930165927.png]]

When the computer reads a value at a **particular index** of an array. It can **jump straight to that index** because:
1. A computer can jump to *any* memory address in *one* step
2. When a computer allocates an array, it **makes note** at which the memory address of the array **begins**.

Say we're looking for the element at **index 3** of the array. The computer finds the index of the first element: **1010** and calculates *1010 + 3* which makes **1013** so the value is **"dates"**.