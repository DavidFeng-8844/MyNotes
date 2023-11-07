#Pointer_Compatibility
> Pointer Can't do type conversion 

Example:
```c
int * pt;  
int (*pa)[3];  
int ar1[2][3];  
int ar2[3][2];  
int **p2; // a pointer to a pointer
//Following value passing methods:
pt = &ar1[0][0]; // both pointer-to-int  
pt = ar1[0]; // both pointer-to-int  
pt = ar1; // not valid  
pa = ar1; // both pointer-to-int[3]  
pa = ar2; // not valid  
p2 = &pt; // both pointer-to-int *  
*p2 = ar2[0]; // both pointer-to-int  
p2 = ar2; // not valid

```
## Functions and Multidimensional Arrays

Declaration: 
You can declare a  function parameter of this type like this:  
```c
void somefunction( int (* pt)[4] );  
```

Alternatively, if (and <mark style="background: #FFB8EBA6;">only if) pt is a formal parameter to a function</mark>, you can declare it as follows:
```c
void somefunction( int pt[][4] );
```

For the compiler to evaluate this, it needs to know the size object  
to which ar points. The declaration
```c
int sum2(int ar[][4], int rows); // valid declaration
``` 
You can also include a size in the other bracket pair, as shown here, but the compiler ignores it:  
```c
int sum2(int ar[3][4], int rows); // valid declaration, 3 ignored
```
This is convenient for those who use typedefs:
```c
typedef int arr4[4]; // arr4 array of 4 int  
typedef arr4 arr3x4[3]; // arr3x4 array of 3 arr4  
int sum2(arr3x4 ar, int rows); // same as next declaration  
int sum2(int ar[3][4], int rows); // same as next declaration  
int sum2(int ar[][4], int rows); // standard form
```
In general, to declare a pointer corresponding to an N-dimensional array, you must supply  
values for all but the leftmost set of brackets::
```c
int sum4d(int ar[][12][20][30], int rows);
```

### Where to place the Asterisk 

==The '*' is associated with the variable name ==
![[Pasted image 20231107214452.png]]