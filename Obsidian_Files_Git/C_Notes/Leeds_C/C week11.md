## How to compile multiple C file 

### Compile Multiple sources 
```bash
gcc mod1.c mod2.c main.c -o dbtest
```

### Re-compiling multiple sources

We can also pass object files to the compiler, which will only
compile the c files, while linking everything at the end:
```bash
gcc mod1.o mod2.c main.o -o dbtest
```

### compiling and linking 
Even if the compiler does not by default keep the objective files,
you can ask it to do so:
```bash
gcc -c mod1.c
gcc -c mod2.c
gcc -c main.c
# And then link:
gcc mod1.o mod2.o main.o -o dbtest
```

### Compiling Unit 

## Static Functions 

---
## Extern Variables 

![[Pasted image 20231120143930.png]]

---
### -E
In the context of the `gcc` compiler, the `-E` option is used to instruct the compiler to stop after the preprocessing stage and output the result to the standard output (usually the console or terminal).
```c
gcc -E source.c
```

## -D 
The `-D` option in the context of the `gcc` compiler is used to define a macro during the compilation process. This option allows you to specify macro definitions directly on the command line. The syntax is as follows:
```c
gcc -D<macro_name>=<value> source.c
```

### ifndef
The `#ifndef` (if not defined) directive is a preprocessor directive in C that checks whether a particular macro is not defined. If the specified macro is not defined, the code between `#ifndef` and a corresponding `#endif` is included during the preprocessing stage. If the macro is defined, the code is skipped.
```c
#ifndef MY_HEADER_FILE
#define MY_HEADER_FILE

// Your header file contents go here

#endif // MY_HEADER_FILE

```


