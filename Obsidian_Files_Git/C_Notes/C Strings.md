# Some key concepts


>Frist way of creating string(just like a normal array)

```c
char str[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '\0'};
```
- 
- ==null terminating character. ==The very last character in the array is `\0` known as the null terminating character. It signifies the end of the string and must be included when creating a string as an initialized array.
> The second way to create a string variable in C is to use what is called a _string literal_. This is the creation of a string by initializing the `char` array with the full string in double quotes like so:

```c
char str[] = "Hello World";
```

 The only benefit to creating a string in this way is that it’s easier to type and ==the null terminating character (‘\0’) is added implicitly.==

### Character Access and Modification 

>It’s important to note that since strings are arrays of characters, they are subject to all of the same constraints as an array. This means a string cannot be extended to add new characters, and a character in a string cannot be deleted!

>When Printing a single character in the string, you should use the specifier ==%c==


## String Length strlen()

we can use the `strlen()` function. This function determines the length of the string. It is used like so:
```c
strlen(str)
```
The `strlen()` function is a special string function contained in the string library. To use it, the code must include the following line at the top of the file:

```c
#include <string.h>
```

>Note that `strlen()` does not account for the null terminating character.

## Using strcat()

The `strcat()` function takes one string, `src`, and appends it to the end of another string, `dst`. Using this function does not create a separate third string, but modifies the `dst` string to include the `src` string at the end. The syntax for this is:

``` c
strcat(dst, src)
```

What actually happens is the function ==takes the two strings and creates a char array of size `strlen(src) + strlen(dst) + 1`. It then populates the array with the characters of both strings starting with `dst`.== Finally, it discards the memory occupied by the original `dst` string and associates the `dst` string variable with the new char array created.

## Copy String using strcpy()

```c
strcpy(dst, src);
```
It is important that the size of the empty character array, `dst`, be greater than or equal to the length of the string `src` plus one for the null character (‘\0’) in order to accommodate all incoming characters. If the `dst` char array is too short, the program will exhibit undefined behavior. Similar to the `strcat()` function, a new string will not be created.


## fgets

### IO 
The system uses buffered I/O. This means the input is stored in temporary memory (the buffer) until the Return key is pressed; this adds a newline character to the input and sends the whole line on to fgets() .


