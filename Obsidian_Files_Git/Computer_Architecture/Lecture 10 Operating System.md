# What is Operating System 

* A program which controls the execution of
all other programs (applications).
 *  Acts as an intermediary between the
user(s) and the computer

![[L10-1.png|300]]

Pros: Convenient Efficiency, control all execution

## Process 

A program in execution 

## Monolithic Operating Systems

user program can abuse computation resources which might trash the entire system 

---
## Dual mode Operating System 

1. Kernel Mode :(On Behalf of the operating system ) 
2. User Mode 
---
## Memory Protection 

==Limiting ==which part of the memory can be accessed by a user program Having a base (start) and a limit (end) registers for each process

---
## Memory Management 

### Fixed (static) sized memory partition

* Physical memory is broken up into fixed partitions
* May not be equal size
* Process is fitted into smallest hole that will take it ==(best fit)
	* So if the memory is larger than the program requires, some memory is wasted 
### Variable size Partitions

>Swapping out : move a process from main memory to disk 


What if there are not enough contiguous memory :![[L10-2.png|400]]
Java: compaceim

---
## Virtual Memory 

Make physical Address looks larger 
Virtual memory address is converted into a physical address (real
address)
![[L10-3.png]]

### Page faults 

A memory is on the disk rather than on the physical memory 

An hardware exception will be generated (which will
be captured by the OS)
•
Current process suspends, others can resume
•
OS moves the data and resumes the suspended process


==•
page = block of consecutive virtual memory
•
frame = block of consecutive of physical memory

---
### Separate Address Spaces

Each process has its own virtual address space

---
### Memory Protection 


Page table entry contains access rights information

---

## Virtual Memory vs. Cache 

It is alike but with difference purpose 

Cache : for performance 
VM: multi-programming and make process access non- contiguous memory 

---
# Page table 

We have one
page table entry (PTE) for each page of the virtual memory


---
## Address Translation 
![[Pasted image 20231019172254.png]]


