J2se is what we use in this course 

## Statement 


## Keywords

Java is case sensitive 
Java is all signed 


## Final 
If you don't want others (or yourself) to overwrite existing values, use the `final` keyword (this will declare the variable as "final" or "constant", which means unchangeable and read-only):

## Declare Many Variables 

Comma-seperated list can be used : 
```java
int x = 5, y = 6, z = 50;
System.out.println(x + y + z);
```

## Data Types

![[Pasted image 20240305204033.png]]
Data types are divided into two groups:

- Primitive data types - includes `byte`, `short`, `int`, `long`, `float`, `double`, `boolean` and `char`
- Non-primitive data types - such as ==String, Arrays==
- A primitive type starts with a lowercase letter, while non-primitive types starts with an uppercase letter.

## Floating point type 
The `float` and `double` data types can store fractional numbers. Note that you should ==end the value with an "f" for floats and "d" for doubles:==
>Float
```java
float myNum = 5.75f;
System.out.println(myNum);
```
>Double
```java
double myNum = 19.99d;
System.out.println(myNum);
```
``
## Java type casting 

Two type of casting widening or narrowing 

### Widening Casting 
Widening casting is done automatically when passing a smaller size type to a larger size type:

### Narrowing Casting
Narrowing casting must be done manually by placing the type in parentheses in front of the value:

```java
public class Main{
	public static void main(String[ args]){
		double myDouble = 9.78d;
		int myInt = (int)myDouble; //Manual Casting
	
	System.out.println(myDouble);
	System.out.println(myInt);
	}
}
```


## String Method 
- length()
- toUpperCase() and toLowerCase()
- indexOf() return the index of the first occurence of a string

## String concatenation 

Can be done with '+'

N.B. 
	If you add a number and a string, the result will be a string concatenation
## Escape Sequences 

![[Pasted image 20240305211115.png]]

## Math Method 

- Math.min()
- Math.max()
- Math.sqrt()
- Math.abs() 
- Math.random()
- 