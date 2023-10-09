# Von Neumann Architecture
![[Pasted image 20231004120752.png|350]]
The **Central Processing Unit (CPU)** consists of:
- **Control unit**
- **Arithmetic/Logic Unit (ALU)**
- **Registers**
	- *Program Counter*: Address of the next instruction
	- *Instruction Register*: Instruction currently being executed or decoded
	- *Address Register*: Either stores the memory address from which data will be fetched, or the address to which data will be sent and stored
	- *Arithmetic Register*: Short-term, intermediate storage of arithmetic and logic data computations
- **System Bus**:
	- *Control Bus*: Carries commands from the CPU and returns status signals from the devices
	- *Data Bus*: Carries the actual data being processed
	- *Address Bus*: Carries memory addressed from the processor to other components
- **Memory (RAM)**
- **Input/Output Units**
- **Clock Cycle**:
	- Signal that oscillates between high and low - used to *synchronise actions*
	- The number of cycles that a CPU uses per second is used to determine its speed in MHZ and GHz
	- The rate of the Fetch/Execute Cycle is determined by the computer's clock

## One Cycle per Clock Tick
A computer with a **1 GHz** clock has one billionth of a second (1 nanosecond) between clock ticks to run the Fetch/Execute Cycle
- Modern computers try to start an instruction on each clock tick
They pass off completing the instruction to other circuitry. This process is called **pipelining** and frees the fetch unit to start the next instruction before the last one is done

![[Pasted image 20231004122934.png]]

# The Harvard Architecture
![[Pasted image 20231004123004.png]]

## Von Neumann vs Harvard
![[Pasted image 20231004123034.png]]

### Case Study: MIPS R4000
Similar to Von Neumann but separate interfaces to instructions and data
- First **64-bit architecture**
- **Integrated caches** (on-chip, off-chip, secondary cache)
- Integrated **Floating Point Unit (FPU)**
- Implemented in **1992**
	- **Deep** pipeline
	- **1.4M transistors**
	- Initially **100MHz**
- **Simple, well-behaved** programming model
- Compact set of instructions with regular format (MIPS III)
- "Easy" to translate from high-level code to machine learning

![[Pasted image 20231004123829.png]]

- 8 stage pipeline (**super-pipelined**)
- Extend **IF** and **MEM** stages to account for cache overheads

![[Pasted image 20231004123927.png]]

#### MIPS R4000 Pipeline Stages
1. **IF**: First half of instruction fetch, PC selection actually happens here, together with initiation of instruction cache access
2. **IS**: Second half of instruction fetch, complete instruction cache access.
3. **RF**: Instruction decode and register fetch, hazard checking, and also instruction cache hit detection
4. **EX**: Execution, which includes effective address calculation, ALU operation, and branch target completion of data cache access
5. **DF**: Data fetch, first half of data cache access
6. **DS**: Second half of data fetch, completion of data cache access
7. **TC**: Tag check, determine whether the data cache access hit
8. **WB**: Write back for loads and register - register operations

![[Pasted image 20231004124347.png]]

#### MIPS R4000 - Key Features
- Program counter, instruction register, control unit, FPU
- 32 x 32 bit/64-bit registers
- CPU registers can be either 32 bits or64 bits wide, depending on the R4000 processor mode of operation
- Arithmetic and Logic Unit
	- Takes input from up to two registers
	- Send output to registers only
	- **one exception**: also used to calculate memory addresses

## Assembly Language
The **binary object** file is the only form a computer can be given software. Computers can be programmed to **translate software** expressed in other forms into binary object code. Assembly language is an alternative form of machine language that uses **letters** and **normal** numbers so people can understand:
- Computer scans assembly code
- As it encounters words it looks them up in a table to convert to binary
- Converts numbers to binary, then assembles (put together) the binary places into an instruction

## Programming Languages
Most modern software is written in a **high-level programming language**. High-level languages are **compiled/translated** into assembly language, which is then **assembled** into binary. These languages are preferred because they have special statement forms that help programmers describe the complicated tasks they want done.

![[Pasted image 20231004125846.png]]

## Instruction Sets
Computers do not understand high-level programming languages by themselves/ Each machine has a **unique instruction set** also known as Instruction Set Architecture (ISA). This is what the programmer "sees" and "uses".

##### Example
To calculate a = b + c
- We need to put **b** and **c** into registers and *load* them from the memory. 
- Add them together and the result will go into a register
- Put the result into the memory location of **a** and store it

![[Pasted image 20231004130936.png]]

![[Pasted image 20231004131012.png]]


