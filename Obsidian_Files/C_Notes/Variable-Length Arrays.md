#VLA

## Impulse for C99 to introduce VLA：
>C is being positioned to take over from FORTRAN, so the ability to convert  FORTRAN libraries with a minimum of fuss is useful.

## Declration:
```c
int sum2d(int rows, int cols, int ar[rows][cols]); // ar a VLA

```
Because the ar declaration uses rows and cols, they have to be<mark style="background: #ABF7F7A6;"> declared  
before ar in the parameter list. </mark>Therefore, the following prototype is in error:
``` c 
int sum2d(int ar[rows][cols], int rows, int cols); // invalid order
```
The C99/C11 standard says you can omit names from the prototype; but in that case, you need  
to replace the omitted dimensions with asterisks:
```c
int sum2d(int, int, int ar[*][*]); // ar a VLA, names omitted
```

## Defining functions:
```c

```int sum2d(int rows, int cols, int ar[rows][cols])  
{  
int r;  
int c;  
int tot = 0;  
for (r = 0; r < rows; r++)  
for (c = 0; c < cols; c++)  
tot += ar[r][c];  
return tot;  
}
````
> VLA support dynamic memory allocation 

Which means the size of the arry can be specified when the program is running.

> const and Array Sizes

Can you use a const symbolic constant when declaring an array?
```c
const int SZ = 80;
//...
double ar[SZ]; // permitted?
```
For C90, the answer is no (probably). The size has to be given by an integer constant expression,
which can be a combination of integer constants, such as 20 , sizeof expressions, and
a few other things, none of which are const . An implementation can expand the range of what
is considered an integer constant expression, so it could permit using const , but the code
wouldn’t be portable.
<mark style="background: #FFB8EBA6;">For C99/C11, the answer is yes, if the array could otherwise be a VLA. So the definition would
have to be for an automatic storage class array declared inside a block.</mark>
