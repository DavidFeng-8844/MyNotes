# Registers

## Evolution of Registers
### Accumulator 
>Ex the AC Button on the calculator is from the original Accumulator on the mechanical calculator 

### Accumulator + address registers 


### GPR


Example C = A + B

LOAD R1, A 
LOAD R1, A
LOAD R2, B 
ADD R3, R1, B

ADD R3, R1, R2 
STORE R3, C
STORE R3, C 5


## Control & Status controller
* PC
* IR 
* MAR
* MBR
![[L5-1.png]]
#dataflow 

## General purpose register 
1. Data 
2. Addressing 
3. Amount : 
4. Size: Large enough to hold full address/word 

## program Status Word Register ==PSW==

1. Store a set of bits 
2. Include Condition codes 

## The instruction cycle 

## Data Flow 
### Instruction fetch
* PC contains address of next instruction
* Address moved to MAR
* Address placed on address bus (memory interconnection)
* Control unit requests memory read
* Result placed on data bus, copied to MBR, then to IR
* Meanwhile PC incremented by 1

### Data Fetch
The operand of an instruction contains a short memory address of a location which itself contains the full memory address of the operand (allowing shorter instructions)![[L5-3.png]]



### Indirect addressing
The operand of an instruction contains a short memory address of a location which itself contains the full memory address of the operand

## pipeline

Laundry Example


Ideal 
* Improve the throughout without adding hardware cost
* Repititionz*

### Prefetch

>Def:

Instruction:
20
FI Fetch instruction
DI Decode instruction
CO Calculate operands (effective addresses)
FO Fetch operands
EI Execute instructions
WO Write result

![[L5-2.png]]
### Control dependence

solutions for branches in pipelines 
