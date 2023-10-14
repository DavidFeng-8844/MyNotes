# Principle of floating point 

>Like a scientific notation:
>$n = f × 10^e$
	where f is called the fraction, or mantissa, and e is a positive or negative integer called the exponent. The range is effectively determined by the number of digits in the exponent and the precision is determined by the number of digits in the fraction.

>**Normalized numbers**
• A number in Scientific Notation with no leading 0s is called a Normalized Number: $1.0 × 10^-8$
![[L3-2.png]]
---
## Overflow and Underflow

### Overflow 

Overflow occurs when the result of an operation, such as addition or multiplication, exceeds the maximum representable value in the floating-point format. This means the value has become too large to be accurately represented with the available bits. Overflow can lead to inaccuracies in calculations and, in some cases, produce special "infinity" values or result in the loss of significant digits.

### Underflow 

Underflow, on the other hand, occurs when the result of an operation is smaller in magnitude than the smallest representable positive value (often called "denormal" or "subnormal" numbers).

![[L3-1.png]]


## Difference between real numbers and Floating point numbers 

1. ==Density==the real numbers form a ==continuum==
2. ==Underflow and overflow ==error

>Key Method ---==Rounding==(Use the nearest number that can be used)
>==Since there is no systematic variation between difference regions of values, the relative error is the same for either small or big numbers>

---
---
# IEEE Floating-Point Standard 754

>General: Consist of three formats: 
1. single precision 32 bits
2. double precision 64 bits
3. extended precision 80 bits

>Component:
1.==start with a sign bit for the number as a whole, 0 being positiv
and 1 being negative.
== 2. The exponent, using ==excess 127 for single precision and excess 1023 for double precision.==
3.Fractions 23 and 52 bits respectively.

>N.B.
>To avoid confusion with a conventional
fraction, the combination of the implied 1, the implied binary point, and the 23 or
52 explicit bits is called a significand instead of a fraction or mantissa


![[L3-3.png]]

>Examples:
>![[L3-4.png]]

## Floating Point Calculations

### Addition and Subtraction

* Exponent and mantissa treated separately 
* Exponents of numbers must agree 
		* Align and binary points(==Smaller exponent is incremented==) 
		* ![[L3-5.png]]
		* least significant digits may be lost
* Add Mantissas using integer addition Mantissa overflow requires==exponent again shifted right==
 ![[L3-6.png]]
### Floating Number Multiplication 

1. Add the exponents as a new one
2. multiply the mantissas 
3. Normalize the result 
4. Adjust the sign 


---
# Floating point Number Comparison
Use the value of a floating point number as condition:
```c
e = a + b;
if (abs(e-0.5) <= 0.0000005){

}
```