---
Module: Computer Systems
Date: 09-10-2023
Topic: Computer Architecture, Machine Code and Program Execution
---
- [x] If somebody asked you what a computer is, how would you identify/describe that?
	A **complex system** that can be instructed to carry out sequences of **arithmetic or logical operations** automatically via computer programming.
	
- [x] Based on your understanding so far of the computer, what are the main requirements of designing a Computing Machine
	- Load program from external device/memory,
	- process instructions in the correct order,
	- access pieces of data in accordance with the program's instructions,
	- perform computations,
	- take decisions according to the results of the computations,
	- send the results of the computations to some external device

- [x] All computers, regardless of their implementation technology, have five basic units or subsystems. What are these units?  
	- Memory
	- Control Unit
	- ALU
	- Input/Output Unit

- [x] How do computers execute programs?
	Program is loaded into memory and address of first instruction is place in the program counter and the Fetch/Execute cycle occurs:
	1. Instruction Fetch
	2. Instruction Decode
	3. Data/Operand Fetch
	4. Instruction Execution
	5. Result Return/Store

- [x] In The von Neumann Architecture the CPU contains some registers. What is the main purposes of having these registers? What will happen if the CPU had to rely on the RAM instead of these registers?
	- Small, fast unit of storage used to hold program data and instructions being executed by the ALU
	- Accessing RAM would take many CPU cycles and would take significantly longer than using registers

- [x] Why is it not quite true to say that 1,000 instructions are executed in 1,000 ticks? 
	- Pipelining breaks down the execution of instructions into multiple stages so multiple instructions can be in different stages of execution simultaneously. 1,000 instructions may be less than 1,000 ticks as multiple instructions are in progress at any given time

- [x] What is the main difference between the von Neumann Architecture and the Harvard Architecture? 
	- Program memory and Data memory are stored separately at the instruction and variable address respectively. This allows Harvard Architecture to be able to fetch instructions and stored data without being bottlenecked.

- [ ] Convert the following Higher-level code to MIPS assembly language code 

``` javaScript
let y = 0
for (i = 1; i <= x; i++) {
	y = y + i
}
```

``` Assembly Language

```

- [ ] Given the MIPS Instruction set, convert the following MIPS assembly code into Java-like code. Note that “bgt” instruction is for “branch greater than” and is used to jump to a label, if a register value is more than the provided constant. You are expected to consider the following register assignment while writing Java code.

|   |   |
|---|---|
|**MIPS Register**|**Java Variable**|
|$1|i|
|$2|tmp|
|$3|sum|

The MIPS Assembly Code is given below

|   |
|---|
|and $1,$1,$0  <br>    and $2,$2,$0  <br>    and $3,$3,$0  <br>label:  <br>    bgt $1,14,exit  <br>    multi $2,$1,2  <br>    add $3,$3,$2  <br>    addi $1,$1,1  <br>    j label  <br>exit|

- [ ] Using the Little Man Computer Simulator ([http://peterhigginson.co.uk/LMC/](http://peterhigginson.co.uk/LMC/)), write LMC assembly programs to compute the following expressions:
    - `e = (a+b)–(c+d)`
        
    - `z = 3x + y`
        
    - `c = a2 + b2`
        
- [ ] Have a look at the above link to read about the LMC and see the instruction set of LMC with some examples.