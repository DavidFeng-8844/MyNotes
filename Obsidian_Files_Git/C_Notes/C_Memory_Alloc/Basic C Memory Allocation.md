
# Basic Concept 

A typical memory representation of a C program consists of the following sections. 
1. Text segment (i.e. instructions)
	As a memory region, a text segment may be placed below the heap or stack in order to prevent heaps and stack overflows from overwriting it.
2. Initialized data segment 
		This segment can be further classified into the initialized read-only area and the initialized read-write area.==a global C statement like const char* string = “hello world” makes the string literal “hello world” to be stored in the initialized read-only area and the character pointer variable string in the initialized read-write area. Ex: static int i = 10 will be stored in the data segment and global int i = 10 will also be stored in data segment==
	  
3. Uninitialized data segment (bss) 
	Uninitialized data segment often called the “bss” segment, named after an ancient assembler operator that stood for “block started by symbol.”==Data in this segment is initialized by the kernel to arithmetic 0 before the program starts executing uninitialized data starts at the end of the data segment and contains all global variables and static variables that are initialized to zero or do not have explicit initialization in source code. For instance, a variable declared static int i; would be contained in the BSS segment.==
4. Heap Heap is the segment where dynamic memory allocation usually takes place.
5. Stack The stack area contains the program stack, a LIFO structure, typically located in the higher parts of memory.

![[Pasted image 20231107221130.png]]



# Reference

1. [Memory Layout of C Programs - GeeksforGeeks](https://www.geeksforgeeks.org/memory-layout-of-c-program/?ref=lbp)
2. 