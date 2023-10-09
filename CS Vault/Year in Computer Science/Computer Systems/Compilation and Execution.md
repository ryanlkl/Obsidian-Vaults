# Levels of Programming Languages
**High** level languages
- These include Java, C/C++/C#, Fortran, Cobol , Pascal
- These languages are easier for humans to understand
**Low** level languages
- Machine code - instructions stored in memory (*opcodes*)
- Hard to read and write by humans
**Assembly Code**
- Can be written or read by humans (using *mnemonics*)

![[Pasted image 20231004212241.png]]

## Converting High Level to Low Level
To execute on a computer we must have *machine code*. Assembly code is translated to machine code to run.
This is done by an:
- **Assembler** (*relocatable code*)
- **Linker**: combines different assembled parts into a Whole
- **Loader**: loads into memory at a given location

![[Pasted image 20231004212501.png]]

## Executing High Level Programs
A **program** written in a high level language can be run in 2 different ways:
1. **Compiled** into a program in the *native machine* language and then run on the target machine
2. Directly **interpreted** and the execution is simulated within an interpreter

### Compilation
**Compiler** converts source code (text of a program) into object code (*machine code*) that does the same thing as the original program.
Usually object code is **relocatable**, so can be later **linked** and **loaded** into memory.

| Advantages                                                                                 | Disadvantages                                             |
| ------------------------------------------------------------------------------------------ | --------------------------------------------------------- |
| Done *once* for each program                                                               | *Harder* than interpreting                                |
| Clever tricks optimise object code so that it will run fast (exploiting hardware features) | Hardware *dependent* so cannot run on different platforms |                                                                                           |                                                           |

Compiler runs on the same platform as the target code:

![[Pasted image 20231004213025.png]]

#### Cross Compilation
Compiler runs on platform X, target code runs on platform Y

![[Pasted image 20231004213105.png]]

## Interpretation
An **interpreter** is another program that follows the source code (text of the program) and does appropriate actions
It is the same principle as:
- Humans running through instructions of a program
- A CPU

| Advantages                                       | Disadvantages    |
| ------------------------------------------------ | ---------------- |
| Facilities **interactive** debugging and testing | *Slow* execution |
| User can **modify** the values of variables and can invoke procedures from the command line                                                 |                  |

![[Pasted image 20231004213329.png]]

## Combined Compilation and Interpretation
When executing high level programs:
- **Compile** to an *intermediate* level language that can be efficiently **interpreted**
This is *slower* than pure compilation but **faster** than pure interpretation. Combined only requires a **single compiler** so it is independent of the CPU and has **separate tasks** for each CPU to interpret the intermediate language.

![[Pasted image 20231004214142.png]]

### Virtual Machines
A **virtual machine** executes an instruction stream in software. This is adopted by Pascal, Java, Smalltalk-80, C#, which are functional and logic languages and some scripting languages.
Pascal compilers generate *P-Code* that can be interpreted or compiled into object code while Java compilers generate *bytecode* interpreted by the **Java Virtual Machine (JVM)**. the JVM may translate *bytecode* into *machine code* by **Just-In-Time (JIT)** compilation.

![[Pasted image 20231004214444.png]]

# Java Virtual Machine (JVM)