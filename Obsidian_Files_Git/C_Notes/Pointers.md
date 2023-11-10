### Pointers Intro

In C, a byte of memory can be accessed using a _pointer_. A pointer containing the address of a variable is said to “point” to that variable.

>Recall that when you declare a variable, a contiguous block of bytes is reserved in memory. A pointer to a variable is the address of the first of these bytes


## Pointer Address and deference

Address &
deference * 

## Pointer Arithmetic

The important thing to note here is that adding `n` to a pointer _does not_ increment the address to point to a value `n` bytes away. It moves the pointer by `n` * (size of the data type in bytes). For example, if a pointer to an `int`, the size of which is four bytes, initially contains address 100 (we will use a decimal address for simplicity), and three is added to the pointer, the pointer will now point to address 112.

---
# Pointers and Array

Consider an array of integers `arr`. Since arrays are contiguous blocks of memory, if we have a pointer to the first element, we can use pointer arithmetic to access the rest of the array.

---
# Review 

Congratulations on completing this lesson on pointers and memory management! Here is a brief recap of everything you’ve learned: 
The base unit of memory is a byte. 
Memory is represented as a block of bytes. 
These bytes have an associated address which is represented by a hexadecimal number. 
When a program is running, it is the responsibility of the underlying operating system to reserve a block of RAM for the program. 
A pointer is a special type of integer variable that stores the memory address of a regular variable. 
A pointer can store the address of any type of variable, including other pointers. 
The address stored in a pointer is the address of the first byte of memory that stores a variable.
A pointer can be declared in two ways: 
dataType* nameOfPointer; 
dataType *nameOfPointer; 
To obtain the address of a variable such that it may be assigned to a pointer, the reference operator (&) is used.
Syntax: &variableName;
Accessing data that is stored in a memory address pointed to by a pointer is done using the dereference operator (*). 
Syntax: * pointerName
Pointer arithmetic is allowed but only for addition and subtraction by an integer.
It is not possible to add/subtract one pointer to/from another pointer. Incrementing or decrementing a pointer is done in the following way: ==pointer += someInteger; pointer -= someInteger; Incrementing/decrementing a pointer changes the address by n times the size of the data type the pointer is pointing to. ==Because an array is stored as a contiguous block of memory, a pointer can be used to traverse it. Great care must be exercised when using a pointer as it is possible to accidentally corrupt data stored in other memory addresses.
