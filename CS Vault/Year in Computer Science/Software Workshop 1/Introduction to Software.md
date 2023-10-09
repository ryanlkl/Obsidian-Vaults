# Fundamental Ideas of Computer Science
Computer Science focuses on a **broad set of interrelated ideas**
Two of the most basic ones are:
1. Algorithms
2. Information processing

## Algorithms
### Example
An example is subtracting two numbers using the column method:
1. Write down the numbers, largest at the top and smaller one at the bottom ensuring the rightmost digits align
2. Start from the right and work left
3. Write down the difference between the digits borrowing a one from the left column when needed
4. If there is no column to the left: stop. Otherwise, move to the left and go back to step 3

In this scenario, the **computing agent** is a human being and the **sequence of steps** is the **algorithm**

### Features
- Finite number of instructions
- Individual instruction is well defined
	- Action described by the instruction can be performed effectively or be executed by a computing agent
- Describes a process that eventually halts after arriving at a solution
- Solves a general class of problems

**Computer** can be **designed to run a small set of algorithms** for performing specialised tasks
## Information Processing
Information is also commonly referred to as **data**.

1. Start with **input**
2. **Transforms** information according to well-defined rules
3. Produces **output**

Algorithm that describes information processing can also be represented as information

## Structure of a Modern Computer System
Modern computer systems consist of **hardware** and **software**
*Hardware* is physical devices required to execute algorithms
*Software* is the set of these algorithms, represented as **programs** in particular **programming languages**
### Computer Hardware
Basic hardware components of a computer include:
	- Memory
	- Central Processing Unit (CPU)
	- Set of input/output devices

Computers can also communicate with the external world through various **ports** that connect them to **networks** and to other devices

![[Pasted image 20230929145103.png|400]]

Computer memory is set up to represent and store information in electronic form. They are stored as patterns of binary digits.

**Random Access Memory** (RAM) is also called **internal** or **primary** whereas **external** or **secondary** memory can be **magnetic, semiconductor, or optical**

![[Pasted image 20230929145329.png|400]]

### Computer Software
- A program stored in computer memory must be represented in binary digits, or **machine code**
- A **loader** takes a set of machine language instructions as input and loads them into the **appropriate memory locations**
- The most important example of system software is a computer's **operating system**
	- This includes **file systems** and **user interfaces**
- Scientists have developed **high-level programming languages** for expressing algorithms
	- These are usually started in **text editors** like VS Code and PyCharm
	- These text editors run a program called a **translator** which converts to program to executable code and checks for any **syntax errors**
	- If no errors are found, the program can be executed by the **run-time system**

![[Pasted image 20230929145846.png|400]]

## History of Computer Science
```timeline-labeled
date: Before 1800
content:
- Mathemticians **discover and use algorithms**
- **Abacus** used as calculating aid
- First **mechanical caluclators** built by **Pascal** and **Leibniz**
![[Pasted image 20230929151817.png|200]]

date: 19th Century
content:
- Jacquards broom
- Babbage's **Analytical Engine**
- **Boole's system of logic**
- Hollerith's **punch card machine**

date: 1930s
content:
- **Turing** publishes results on **compatability**
- Shannon's **theory of information and digital switching**

date: 1940s
content:
- First **electronic digital computers**

date: 1950s
content:
- **First symbolic programming languages**
- **Transistors** make computers smaller, faster, more durable, and less expensive
- Emergence of **data processing applications**

date: 1960-1975
content:
- **Integrated circuits** accelerate the miniturisation of hardware
- **First minicomputers**
- **Time-sharing** operating systems
- **Interactive** UI using keyboard and mouse
- Proliferation of high-level programming languages
- Emergence of **software industry** and the academic study of computer science

date: 1975-1990
content:
- First **microcomputers** and mass-produced **personal computers**
- GUI becomes widespread
- **Networks and the internet**

date: 1990-2000
content:
- **Optical storage** for multimedia applications, images, sound, and video
- **World Wide Web**, Web applications and eCommerce
- **Laptops**

date: 2000-present
content:
- **Wireless computing**, smartphones, and mobile applications
- Computer embedded and networked in an enormous variety of cars, household appliances, and industrial equipment
- Social networking, use of big data in finance and commerce
- **Digital streaming** of music and video
```

## Python Programming
- Python is a **high-level**, general-purpose programming language for solving problems on modern computer systems
- It is an **interpreted** language

- **Outputting**
```python
print(<expression>)
```

- **Inputting**
```python
input(<prompt>)
```

Inputting **always stores it's variable as a string** so they must be converted.

Use the functions below to convert types:

| Function          | What it does                            |
| ----------------- | --------------------------------------- |
| float(input)      | Converts data to a floating-point value |
| int(input)        | Converts data to an integer value       |
| string1+string2 | Concatenates 2 strings together         |

### Detecting and correcting syntax errors
**Syntax errors** occur when the code written does not follow the language's rules