# What is a Computer?
A computer is a **complex system** that can be instructed to carry out **sequences of arithmetic or logical operations** automatically via computer programming.
## How do Computers Execute Programs?
### Requirements of a Computing Device
- Load program from external device/memory
- Process instructions in the correct order
- Access pieces of data in accordance with the program's instructions
- Perform computations
- Take decisions according to the results of the computations
- Send the results of the computations to some external device

### Anatomy of a Computer System
All computers have **5 basic parts**:
1. Memory
2. Control Unit
3. Arithmetic/Logic Unit (ALU)
4. Input Unit
5. Output Unit

![[Pasted image 20231003215019.png|350]]

##### Memory
Stores both the **program** while it's running and the **data** on which programs operates

**Discrete Locations**: Memory is organised as a *sequence* of discrete locations. In modern memory, each locations is composed of *1 byte*
**Addresses**: Every memory location has an address, these consist of *whole numbers* starting from 0.
**Values**: Memory locations record / store values
**Finite Capacity**: Memory locations have a *finite capacity*. Data may *fit* in the memory location

![[Pasted image 20231003215521.png]]

Blocks of four/eight bytes are used as a unit so they are called *memory words*.
###### Random Access Memory (RAM)
**RAM** is measured in bytes, kilobytes, megabytes, etc.
Lots of memory is needed to handle the space required of programs and data
##### Control Unit
Where the Fetch/Execute Cycle occurs
- Circuitry fetches an instruction from memory and performs the other operations of the Fetch/Execute Cycle on it
- Typical machine instruction has the form "ADD 4000,2000,2080"
	- What this means is that whatever numbers are stored in memory locations 2000 and 2080 wil be added together and stored at 4000

![[Pasted image 20231003220035.png]]

##### Arithmetic/Logic Unit (ALU)
It can add/subtract two numbers. Circuit uses *logic gates* or simpler circuits that implement operations like **and** and **or**. There are also circuits for multiplying, comparing 2 numbers, etc.
The ALU carries out each machine instruction with a separate circuit.
##### Input/Output Units
These 2 components are the wires and circuits through which information moves in and out of a computer. Computer without input or output is useless.
##### The Peripherals
Connect to the computer input/output ports; provide input; and receive output. They are not considered part of the computer.
Some examples include: keyboard, mouse, monitor, USB, hard disks, network cards, etc.

## Executing Programmes
A program is **loaded** into memory and **address of first instruction** is placed in PC (Program Counter).
The Fetch/Execute cycle is as follows:
1. Instruction Fetch (IF)
2. Instruction Decode (ID)
3. Data/Operand Fetch (DF/OF)
4. Instruction Execution (EX)
5. Result Return/Store (RR/ST)

![[Pasted image 20231003221255.png]]

##### Example
ADD 800, 428, 884 stored at 2200
###### Instruction Fetch (IF)
Execution begins by moving the instruction at the address given by the PC from memory to the control unit. Bits of instruction are placed into the decoder circuit of the Control Unit. Once instruction is fetched, the PC can be readied for fetching the next instruction.
###### Instruction Decode (ID)
Decoder determines *what operation* the ALU will perform (ADD), and sets up the ALU. Decoder finds the memory address of the instruction's data (*source operands*).
- Most instructions operate on two data values stored in memory (like ADD), so must instructions have addresses for two source for operands
- These addresses are passed to the circuit that fetches them from memory during the next step
Decoder finds the *destination address* for the Result Return step and places the address in the RR circuit.
###### Data Fetch (DF)
The *data values* to be operated on are retrieved from memory. Bits at specified memory locations are copied into locations in the ALU circuitry. Data values remain in memory (*they are not destroyed*)
###### Instruction Execution (EX)
For the ADD instruction, the addition circuit adds the two source operands together to produce their sum. The sum is then held in the *ALU* circuitry. This is the *actual computation*.

###### Result Return (RR)
RR returns the result of *instruction execution* to the memory location specified by the destination address. Once the result is stored, the cycle begins again.

##### Many Simple Operations
- Computers **know** very few instructions
- Decoder hardware in the controller recognises and the ALU performs only 100 or so different instructions
- Everything that computers do must be reduced to some **combination** of these primitive, hardwired instructions
- ADD is representative of the complexity of computer instructions... some are **slightly simpler**, some *slightly more complex*
- Computers achieve success at what they can do with speed i.e. **millions/billions** of instructions per second

##### Computer's View of Software
A computers sees software as a long sequence of 4-byte (32-bits) groups of bits
**Once installed**, the computer runs the software by:
- Copying the binary instructions into the RAM
- Executing (running) them using the Fetch/Execute Cycle