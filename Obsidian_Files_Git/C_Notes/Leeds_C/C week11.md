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