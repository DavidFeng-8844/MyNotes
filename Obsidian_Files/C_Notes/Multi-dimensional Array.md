# Multi-dimensional #Array 

Examples:
```c
/* zippo1.c -- zippo info */  
#include <stdio.h>  
int main(void)  
{  
int zippo[4][2] = { {2,4}, {6,8}, {1,3}, {5, 7} };  
printf(" zippo = %p, zippo + 1 = %p\n",  
zippo, zippo + 1);  
printf("zippo[0] = %p, zippo[0] + 1 = %p\n",  
zippo[0], zippo[0] + 1);  
printf(" *zippo = %p, *zippo + 1 = %p\n",  
*zippo, *zippo + 1);  
printf("zippo[0][0] = %d\n", zippo[0][0]);  
printf(" *zippo[0] = %d\n", *zippo[0]);  
printf(" **zippo = %d\n", **zippo);  
printf(" zippo[2][1] = %d\n", zippo[2][1]);  
printf("*(*(zippo+2) + 1) = %d\n", *(*(zippo+2) + 1));  
return 0;  
}
```

The out put:
```
zippo = 0x0064fd38, zippo + 1 = 0x0064fd40  
zippo[0] = 0x0064fd38, zippo[0] + 1 = 0x0064fd3c  
*zippo = 0x0064fd38, *zippo + 1 = 0x0064fd3c  
zippo[0][0] = 2  
*zippo[0] = 2
**zippo = 2  
zippo[1][2] = 3  
*(*(zippo+1) + 2) = 3
```



	Particularly, the pointer notation equivalent of zippo[2][1] is 
	*(*(zippo+2) + 1  
1). Break it down：

|zippo| the address of the first two-int element|
|:---:|:---:|
|zippo+2| the address of the third two-int element|  
| *(zippo+2)  | the third element, a two-int array, hence the address of its first element, an int  |
|*(zippo+2) + 1 |the address of the second element of the two-int array, also an int|  
| ``*(*(zippo+2) + 1)`` |the value of the second int in the third row (zippo[2][1])|


![[Screenshot 2023-08-31 143938.png]]

## Pointer to Multidimensional array

>Declaration, still use zippo as example:

>>Zippo is the address of its first element, which is an array of two  
ints. Hence, pz must point to an array of two ints, not to a single int. Here is what you can  
do:  
```c
int (* pz)[2]; // pz points to an array of 2 ints
```

This statement says that pz is a pointer to an array of two ints. Why the parentheses? <mark style="background: #FFB8EBA6;">Well,  [ ]  
has a higher precedence than * . </mark> Therefore, with a declaration such as  
```c
int * pax[2]; // pax is an array of two pointers-to-int
```
apply the brackets first, making pax an array of two somethings. Next, apply the * ,  
making pax an array of two pointers. Finally, use the int, making pax an array of two pointers  
to int.  This declaration creates two pointers to single ints, but the original version uses parentheses to apply the * first, creating one pointer to an array of two ints.

Sample Code:
```c

/* zippo2.c -- zippo info via a pointer variable */  
#include <stdio.h>  
int main(void)  
{  
int zippo[4][2] = { {2,4}, {6,8}, {1,3}, {5, 7} };  
int (*pz)[2];  
pz = zippo;  
printf(" pz = %p, pz + 1 = %p\n",  pz, pz + 1);  
printf("pz[0] = %p, pz[0] + 1 = %p\n",  pz[0], pz[0] + 1);  
printf(" *pz = %p, *pz + 1 = %p\n",  
*pz, *pz + 1);  
printf("pz[0][0] = %d\n", pz[0][0]);  
printf(" *pz[0] = %d\n", *pz[0]);  
printf(" **pz = %d\n", **pz);  
printf(" pz[2][1] = %d\n", pz[2][1]);  
printf("*(*(pz+2) + 1) = %d\n", *(*(pz+2) + 1));  
return 0;  
}
```

Here is the new output:  
```c
pz = 0x0064fd38, pz + 1 = 0x0064fd40  
pz[0] = 0x0064fd38, pz[0] + 1 = 0x0064fd3c  
*pz = 0x0064fd38, *pz + 1 = 0x0064fd3c  
pz[0][0] = 2  
*pz[0] = 2  
**pz = 2  
pz[2][1] = 3  
*(*(pz+2) + 1) =3
```
	As promised,  you can use notation such as pz[2][1], even though pz is a pointer, not an array name. More  generally, you can represent individual elements by using array notation or pointer notation  with either an array name or a pointer:  
```c
zippo[m][n] == *(*(zippo + m) + n)  
pz[m][n] == *(*(pz + m) + n)
```