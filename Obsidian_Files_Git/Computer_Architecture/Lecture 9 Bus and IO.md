
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


## Programmed IO 

•
The CPU waits for the I/O module
to complete operation Polling so not so efficient

## Addressing memory mapped I/O Devices

Under memory mapped I/O, data
transfer is very like memory access.
•
Each device is given a unique identifier
(
•
The CPU commands contain the
identifier.
•
Each I/O device interprets the address
lines on the bus to determine if a
command is for itself.