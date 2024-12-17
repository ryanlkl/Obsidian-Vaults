# Problem

You are given a singly linked list and two integers **start_index** and **end_index**.  
  
Your task is to write a method **reverse_between** within the **LinkedList** class that reverses the nodes of the linked list from **start_index** to  **end_index** (inclusive using 0-based indexing) in one pass and in-place.  
  
**Note:** **the Linked List does not have a** **tail** **which will make the implementation easier.  
  
Assumption**: You can assume that **start_index** and **end_index** are **not** out of bounds.

**Input**

- The method `**reverse_between**` takes two integer inputs `**start_index**` and `**end_index**`.
    
- The method will only be passed valid indexes (you do not need to test whether the indexes are out of bounds)
    

**Output**

- The method should modify the linked list in-place by reversing the nodes from `**start_index**` to  `**end_index**`.
    
- If the linked list is empty or has only one node, the method should return `**None**`.
    
  
**Example**

Suppose the linked list is `**1 -> 2 -> 3 -> 4 -> 5**`, and `**start_index = 2**` and `**end_index = 4**`. Then, the method should modify the linked list to `**1 -> 2 -> 5 -> 4 -> 3**` .

**Constraints**

- The algorithm should run in one pass and in-place, with a time complexity of O(n) and a space complexity of O(1).

# Solution
``` Python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None
        
class LinkedList:
    def __init__(self, value):
        new_node = Node(value)
        self.head = new_node
        self.length = 1
        
    def reverse_between(self, start_index, end_index):
        if self.length <= 1:
            return
        
        dummy = Node(0)
        dummy.next = self.head
        prev_node = dummy
        
        for _ in range(start_index):
            prev_node = prev_node.next
        
        curr = prev_node.next
        
        for _ in range(end_index - start_index):
            move_node = curr.next
            curr.next = move_node.next
            move_node.next = prev_node.next
            prev_node.next = move_node
        
        self.head = dummy.next

```

# Explanation

1. **Start and End Points**: the start_index and end_index
2. **Is the Line too Short?**: Check if the length of the linked list is less than 2
3. **Dummy**: Helper Block
4. **Finding the Block before start**: prev_node is the node before the start_index
5. **Finding the start block**: The node after prev_node
6. **Flipping**:
	1. The game takes the next node
	2. Unhooks the next and moves it after the prev
	3. Repeats until it reaches the index

## **Detailed Walkthrough:**

Preliminary Steps:

**1. Check if the list is empty or has only one node:**

1. if self.length <= 1:
2.     return

It's pointless to reverse if there's only one or no nodes.  

**2. Create a dummy node:**

1. dummy_node = Node(0)
2. dummy_node.next = self.head

This dummy node simplifies our code, especially if we need to reverse from the start of the list.  

Preparation:

**3. Navigate to the Preceding Node**:

     Move to the node right before where the reversal starts.

1. previous_node = dummy_node
2. for i in range(start_index):
3.     previous_node = previous_node.next

Here, if we're reversing from index 1 onwards, `**prev**` will point to node 1 (index 0).  

**4. Set** `**current**` **to the node at position** `**m**`**:**

1. current_node = previous_node.next

`**currentNode**` now points to the node at the index of 1, where our reversal starts.  

The Core Loop:

**5. Reverse nodes between** `**start_index**` **and** `**end_index**`**:**

1. for i in range(end_index - start_index):
2.     node_to_move = current_node.next
3.     current_node.next = node_to_move.next
4.     node_to_move.next = previous_node.next
5.     previous_node.next = node_to_move

Using our example, where we reverse nodes at indices 1 through 3:

  

**First iteration** (Reversing node at index 2, i.e., node 3):

- `**node_to_move**` will first point to node 3.
    
- Node 2 (`**current_node**`) will then point to node 4.
    
- Node 3 (`**node_to_move**`) will point to node 2.
    
- Node 1 (`**previous_node**`) points to node 3.
    
    Result: `**1 → 3 → 2 → 4 → 5**`.
    

  

**Second iteration** (Reversing node at index 3, i.e., node 4):

- `**node_to_move**` will next point to node 4.
    
- Node 2 (`**current_node**`) will then point to node 5.
    
- Node 4 (`**node_to_move**`) will point to node 3.
    
- Node 1 (`**previous_node**`) points to node 4.
    

Result: `**1 → 4 → 3 → 2 → 5**`.  
This is our desired reversed sequence!

  

**Finalization:**

**6. Reset the head:**

1. self.head = dummy_node.next

This ensures the head now correctly points to the new start of the list if the reversal included the original first node.

Visualizing this with diagrams on paper or on a board is usually very helpful. Consider each node as a box and each pointer as an arrow. Move the boxes around as you progress through the code, and redraw the arrows according to where the pointers point.

1 2 3 4 5