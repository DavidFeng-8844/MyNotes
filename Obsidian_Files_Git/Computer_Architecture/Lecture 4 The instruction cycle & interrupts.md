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

3.  Registers ![[L4-2.png|200]]
**Registers**  are small, fast storage locations within the CPU. They are used to store data temporarily during processing. There are different types of registers in a CPU:

- **General-Purpose Registers:** These registers are used to store data that the CPU is currently processing. Examples include the Accumulator, Data Register, and Address Register.
    
- **Instruction Register (IR):** The instruction register is a special register that holds the current instruction being executed. The control unit fetches instructions from memory and loads them into the IR.
    
- **Program Counter (PC):** The program counter is another special register that keeps track of the address of the next instruction to be executed. When an instruction is fetched from memory, the PC is incremented to point to the next instruction.
Computer ==loads data from RAM to registers (or AC)== and perform operations on data in registers and ==stores the result in RAM.== 
4. **Memory:** The CPU interacts with memory to fetch instructions and data. The control unit is responsible for coordinating these interactions.
 
 
 ### >How these components work together in a simplified CPU operation:

1. The program counter ==(PC) points to the memory address of the next instruction ==to be executed.
    
2. The control unit ==fetches the instruction from that memory location and loads it into the instruction register (IR).==
    
3. The control unit ==decodes the instruction in the IR ==to determine what operation needs to be performed and which operands to use.
    
4. If the instruction involves arithmetic or logic operations,==the control unit instructs the ALU  perform the operation using data from the general-purpose registers.==
    
5. The result of the operation is stored back in the registers if necessary, and==the program counter (PC) is updated to point to the next instruction.==
 ![[L4-4.png|300]]![[L4-5.png|300]]

Examples:
C $\Leftarrow$ a + b

![[L4-3.png]]



* Instruction Resiter IR 
* PC program counter 
* AC Accumulator 

**A certain Instruction pattern**
•The ==contents of PC's memory address are interpreted as an instruction.==
•The most significant bits provide the ==opcode (Operation code)==.
•The remaining bits give a memory address.
•The contents of this address will be interpreted as data (often as operand).

>Example See Lecture 4 Ex 1
>
## Interrupts

### Multiple interrupts

Priority: lower priority interrupts can be interrupted by the higher prioritized ones













# References: 
1. ChatGPT Prompt: Is instruction Resgisters and program counter in ALU or somewhere else, please explain the CPU architecture to me
2. Web: https://www.edrawsoft.com/article/computer-architecture.html
