
# Basic Ideas 
![[Pasted image 20231018110455.png]]

# Bandwidth, Delay and Throughput

1. Bandwidth represent the amount of data can be transferred at once 
2. Clock speed 
3. Through = Bandwidth $\times$ Clock width

---
# The System Bus

A system bus connects major components.
•
It typically consists of 50 100s of separate lines.
•
Each line has a particular meaning or function

---
# Serial vs Parallel 

>==Serial==: one at  time 
>==Parallel: ==multiple lines at the same time 


It becomes difficult to sync among parallel lines as the clock speed increases Hence, serial
transmissions have started to replace parallel communications

--- 
# Bus scalability 

Different bus with different hierarchy and speed

---
---

# Input and Output Interfaces 

---
## Programmed IO 

* The CPU waits for the I/O module to complete operation Polling so not so efficient
	* Often in embedded system with single input output instruction
 ==The primary disadvantage== of programmed I/O is that the CPU spends most of
its time ==in a tight loop waiting for the device to become ready==. This approach is
called ==busy waiting.==

* The way to get rid of busy waiting is to have the CPU start the I/O device and
tell it to generate an interrupt when it is done
---
## Addressing memory mapped I/O Devices

>Under memory mapped I/O, data
transfer is very like memory access.

* Each device is given a unique identifier
* The CPU commands contain the
identifier.
* Each I/O device interprets the address
lines on the bus to determine if a
command is for itself.


#Questions: Why Load/store to mmap locations can have side effects


## Interrupt Driven IO 
By setting the INTERRUPT ENABLE bit in a device register, the software
can request that the hardware give it a signal when the I/O is completed.
The problem is that an interrupt is required for every
character transmitted. Processing an interrupt is expensive. A way is needed to get
rid of most of the interrupts.

## Direct Memory Access

* Require a DMA Controller (Chips) 
* DMA performs transfer while CPU does other processes 
* DMA sends interrupt when completed






Reference: Structured Computer Organization P.394