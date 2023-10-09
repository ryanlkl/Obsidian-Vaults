---
Module: Software Workshop 1
Date: 09-10-2023
Topic: Strings and Text Files
---
### Learning Objectives
`fas:Star` Access individual characters in a string
`fas:Star` Retrieve a substring from a string
`fas:Star` Search for a substring in a string
`fas:Star` Convert a string representation of a number from one base to another
`fas:Star` Use string methods to manipulate strings
`fas:Star` Open a text file for output and write strings or numbers to the file
`fas:Star` Open a text file or input and read strings or numbers from the file
`fas:Star` Use library functions to access and navigate a file system
# Strings and Text Files
## The Structure of Strings
A string is a **data structure**. so each value is stored at an index.

![[Pasted image 20231001152226.png|300]]

Use the **subscript operator** to select certain elements

``` Python
string = "Hi there!"
string[0] # "H"
string[-1] # "!"
string[0:2] # "Hi "
string[-3:] # "re!"
```

### Data Encryption
Data traveling on the internet is **vulnerable** so people use **data encryption** to protect information transmitted on networks.

An example of this is the <strong>Caesar Cipher</strong>.

![[Pasted image 20231008124018.png]]

``` Python
message = input("Enter your message: ")
distance = int(input("Enter the distance value: ")) % 26
letters = "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"
encrypted = ""

for l in message:
	if l != " ":
		value = letters.index(l) + distance
		encrypted += letters[value]
print(encrypted)
```
### Strings and Number Systems
Representing [[Numbers|numbers]].
#### String Methods
``` Python
s.center(width)
# Returns a copy of s centered withing the given number of columns

s.counter(sub[,start[,end]])
# Returns number of non-overlapping occurences of substring sub in s

s.endswith(sub)
# Returns True if s ends with sub or Flase otherwise

s.find(sub[,start[,end]])
# Returns lowest index in s where substring sub is found

s.isalpha()
# Returns True if s contains only letters or False otherwise

s.isdigit()
# Returns True if s contains only digits or False otherwise

s.join(sequence) *
# Returns a string that is concatenated with separator being s

s.lower() *
# Returns a copy of the string in lower case

s.replace(old,new[,count]) *
# Returns a copy of s with all occurences of substring old replaced by new

s.split([sep]) *
# Splits s with separator sep

s.startswith(sub)
# Returns True if s starts with sub or False otherwise

s.strip([aString]) *
# Returns copy of s without leading and trailing whitespace, if aString added, aString is also removed

s.upper()
# Returns a copy of s converted to upper case
```
### Text Files
#### Writing
``` Python
f = open("myFile.txt","w") # Open file to write to it
f.write("First line. \nSecond line.\n") # Write to file
f.close() # Close file
```
#### Reading
``` Python
f = open("myFile.txt","r") # Open file to read from it
for line in f: # Loop over lines
	print(line) # Print individual lines
```
### Alternate method to accessing files
``` Python
with open("myFile.txt","w") as f:
	f.write("First line. \nSecond line.\n")
# Automatically closes file after use
```
### Accessing Files
![[Pasted image 20231008132511.png]]

![[Pasted image 20231008132524.png]]

![[Pasted image 20231008132542.png]]
