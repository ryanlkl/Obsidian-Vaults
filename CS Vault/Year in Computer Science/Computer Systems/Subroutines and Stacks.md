---
Module: Computer Systems
Date: 09-10-2023
Topic: Subroutines and Stacks
---
- [ ] To introduce the fundamental concepts of *subroutines*
- [ ] To understand how subroutines are implemented using *stacks*

# Subroutines
## Example
``` Python
def myFunction():
	# Function body

if __name__ == "__main__":
	myFunction()		
```

![[Pasted image 20231009222158.png|500]]

![[Pasted image 20231009222226.png|500]]

![[Pasted image 20231009222246.png|500]]

You must store the **return address** somewhere.

## Call/Return Instructions
**Two new operations**:
- **Call** operand: Stores current PC value (return address) *somewhere suitable*
- **Ret** operand: Read return address from where it was stored, and load in into PC

## Storing the Return Address
### Idea 1
In each subroutine, its first byte is used to store the return address
**call 94**:
	- Stores return address at 94
	- Starts executing at 95
**ret 94**:
	- Loads pc with return address at 94
#### Disadvantages
- Can only store one return address
- Consequence: subroutine *cannot call itself*
	- If it were to call itself it would need to store 2 return addresses

![[Pasted image 20231009232908.png]]

### Idea 2
Store the *return address* on a [[Stacks|stack]].
**call N**:
	- push pc // push program counter
	- ld pc N // jump to N
**ret**:
	- pop pc // pop return address and jump to it

#### Why should we save registers?
- Subroutine may need to use registers for its calculations
	- Previous register values are needed on return
- Common pattern for subroutines:
	- Start by pushing all registers
	- Pop them back before return
- Return address and saved registers = **stack frame**

![[Pasted image 20231009233247.png|550]]

![[Pasted image 20231009233308.png|550]]

### Example:
[[150. Evaluate Reverse Polish Notation]]

#### Stack instead of registers (Stack Machines)
- Use 2 stacks
	- **return** stack for subroutine return
	- **operand** stack for Reverse Polish calculations
- Don't need a,b,c registers

| Advantages                  | Disadvantages                                    |
| --------------------------- | ------------------------------------------------ |
| More space for calculations | Harder to know where the things are on the stack |
| Opcodes don't need to specify registers                            |                                                  |

#### What is an operand?
**Extra bytes** after the instruction opcode in memory (e.g. Id a *42*)
**Entries** in the operand stack

## Bitwise Boolean Operations

| OR  | 0   | 1   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 1    |1     |1     |

| AND | 0   | 1   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 1    0|     | 1    |

| XOR | 0   | 1   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 1    | 1    |0     |

### Jumps
- **Unconditional jumps**
	- Operand stack is not used
- Conditional jumps