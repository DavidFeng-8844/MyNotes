
# define Directives
The ‘#include’ directive request the inclusion of a header file into your program
>Using angle brackets (< >). This is used for system header files. It searches for the file in a standard list ofsystem directories.

>Using quotes(" "). This is used for your own header files. It searches for the file in the directorycontaining your C source file, and if not found it searches for it in the system directories.

>#undef gets rid of a macro

## Some standard Macros 

![[Pasted image 20231009142457.png]]

# The #if directive

The #if tests a compile time condition, and if the condition is true, the code immediatelyfollowing the #if directive is compiled.
•The syntax for the #if directive is:
```c
#if expression
// Some code
#endif
```

#ifdef/#ifndef

```c
#ifdef macro_name
    // Code to include if macro_name is defined
#else
    // Code to include if macro_name is not defined
#endif

```