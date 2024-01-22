# Instruction set architecture

Instruction Set Architecture (ISA) is the structure of a computer that a machine language programmer (or a compiler) must understand to write a correct (timing independent) program for that machine

--IBM, Introducing the IBM 360 (1964) ISA

# Stack Architecture 

## Registers 


## RISC: reduced instruction set computer


* Simple implementation
* Register register, fixed format 32 bit instructions, efficient pipelines
* Compilers do the hard work

## X86 X86: complex instruction set computer CISC

>Variable length ISA (1 16 bytes)



---
## Evolution of ISA 
1. 
2. why become complicated: Assembly programming
3. Simple again : memory increase 

---
## why it doesn't matter now 

>Decode CISC instructions into interna ISA (in RISC) 
>Pros: 
External ISA for compatibility, internal ISA can be tweaked each generation

## Byte ordering 

* Big Endian 
  Least Significant byte has the highest memory address 
* Little Endian 
  least significant byte has the lowest memory address 
  ![[L6-1.png]]
  