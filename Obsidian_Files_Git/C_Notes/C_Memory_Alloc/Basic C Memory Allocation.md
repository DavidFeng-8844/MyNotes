
# Basic Concept 

A typical memory representation of a C program consists of the following sections. 
1. Text segment (i.e. instructions)
	As a memory region, a text segment may be placed below the heap or stack in order to prevent heaps and stack overflows from overwriting it.
2. Initialized data segment 
		This segment can be further classified into the initialized read-only area and the initialized read-write area.==a global C statement like const char* string = “hello world” makes the string literal “hello world” to be stored in the initialized read-only area and the character pointer variable string in the initialized read-write area. Ex: static int i = 10 will be stored in the data segment and global int i = 10 will also be stored in data segment==
	  
3. Uninitialized data segment (bss) 
	Uninitialized data segment often called the “bss” segment, named after an ancient assembler operator that stood for “block started by symbol.”==Data in this segment is initialized by the kernel to arithmetic 0 before the program starts executing uninitialized data starts at the end of the data segment and contains all global variables and static variables that are initialized to zero or do not have explicit initialization in source code. For instance, a variable declared static int i; would be contained in the BSS segment.==
4. Heap Heap is the segment where dynamic memory allocation usually takes place.
	- Program memory is organized into two main categories: the stack and the heap. A stack is a section of memory that is highly ordered and data stored on the stack are only available within a certain scope (you’ll learn about this in the lesson on functions). In contrast, the heap is not as ordered as a stack. When you create a variable in the usual way, you are statically allocating memory and it is stored on the stack. That memory will be released by the program when the variable is no longer needed. The heap allows you to reserve as much available memory as you want and that memory will remain available until you explicitly release it. This is known as dynamically allocating memory. Forgetting to release dynamically allocated memory will cause a memory-leak leading to poor program performance.
	- 
1. Stack The stack area contains the program stack, a LIFO structure, typically located in the higher parts of memory.

![[Pasted image 20231107221130.png]]


---
## Functions
These functions are stored in the `stdlib` library. To use them, you must import this library.

You will need a pointer to work with the memory provided by any of these functions.

|Function|Use Case|
|---|---|
|`malloc()`|Use this function to reserve as many bytes as you want on the heap|
|`calloc()`|Use this function to reserve memory for some number of `int`s, `double`s, or any other data type.|
|`realloc()`|Use this function to expand or contract a block of reserved memory (reserved by either `malloc()` or `calloc()`).|
|`free()`|Use this function to release previously allocated memory.|
# Reference

1. [Memory Layout of C Programs - GeeksforGeeks](https://www.geeksforgeeks.org/memory-layout-of-c-program/?ref=lbp)
2. 