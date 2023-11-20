# Struct Composite 

>Example:

```c
struct Directoryentry{
	char name[50];
	char file[20];
}
```
## Declaring And Initializing Struct

>Struct variables can be declared immediately after the struct declaration itself, for example:
```c
structTime {
	short inthours;
	short intminutes;
	short intseconds;
} t1 , t2 , t3;// t1, t2, and t3 are variables of type structTime;
```

---
## Accessing Struct Member

Individual members of a struct can be accessed used the dot operator (.),
```c
structDate d;
d.day= 10;
d.month= 12;
d.year= 1964;
printf("%i/%i/%i" , d.day, d.month, d.year);// 10/12/1964 will be printed
```

---
## Nested Struct
```c
structDirectoryEntry{
	char name[50]; // the subscriber's name
	struct{ // this structis declared within DirectoryEntry
		inthouse_number;
		char street_name[50];
		char city[20];
		char post_code[8];
	}address;// the address member itself
	char number[14];// the subscriber's phone number
};
```
---
---
# The Typedef Statement 

>The tyepdef statement can be used to add new type names to a C program

 >Example: 
 
```c
typedeffloat real;// define realas a new type equivalent to float
typedeflong intBigInteger; // define BigIntegeras a new type equivalent to long int
```
The typedef statement is very useful with struct declarations to create a single identifier for common types, for example:
```c
typedefstruct{
	intx;
	inty;
	intz;
} Point; // Point is a new type equivalent to struct{intx; inty; intz}
```

==SO== You can do: 
```c
point p1, p2, p3;//declare the varibles or type point 
```