## Harvard Architecture 

Memory not store in the same place, so that the hardware can protect the data and avoid safety issues 

## Von Neuman Concepts 
* Data and instructions are both stored in the main memory
* Content of the memory is addressable by location 
* Instruction are addressed sequentially

## Programming
* Configure the hardware to carry out a specific task 
* Made up of ==instructions==*
## Computer Components

> CPU
 Component:
 1. Control Unit==CU== (The control unit is responsible for managing and coordinating the activities of the CPU. It controls the flow of data and instructions between the CPU's various components.
 2. The ALU is responsible for performing arithmetic and logical operations, such as addition, subtraction, AND, OR, etc. It is the core of the CPU that actually processes data. ==The ALU receives data from registers, performs operations on them, and stores the result back in registers.==
 
![[L4-1.png]]

3.  Registers ![[Pasted image 20231015123945.png|200]]
**Registers**  are small, fast storage locations within the CPU. They are used to store data temporarily during processing. There are different types of registers in a CPU:

- **General-Purpose Registers:** These registers are used to store data that the CPU is currently processing. Examples include the Accumulator, Data Register, and Address Register.
    
- **Instruction Register (IR):** The instruction register is a special register that holds the current instruction being executed. The control unit fetches instructions from memory and loads them into the IR.
    
- **Program Counter (PC):** The program counter is another special register that keeps track of the address of the next instruction to be executed. When an instruction is fetched from memory, the PC is incremented to point to the next instruction.
Computer ==loads data from RAM to registers (or AC)== and perform operations on data in registers and ==stores the result in RAM.== 

### The ALU:
1. ==Instruction Registers (IR)==
-- TO hold the current instruction
3. ==Program Counter (PC)== 
-- to hold the momery address of the instruction to be executed



>> Control Unit 
>> e.x. fetch pc execute 


* Instruction Resiter IR 
* PC program counter 
* AC Accumulator 

## Interrupts

### Multiple interrupts

Priority: lower priority interrupts can be interrupted by the higher prioritized ones
