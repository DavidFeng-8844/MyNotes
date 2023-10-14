# Principle of floating point 

>Like a scientific notation:
>$n = f × 10^e$
	where f is called the fraction, or mantissa, and e is a positive or negative integer called the exponent. The range is effectively determined by the number of digits in the exponent and the precision is determined by the number of digits in the fraction.

>**Normalized numbers**
• A number in Scientific Notation with no leading 0s is called a Normalized Number: $1.0 × 10^-8$

---
## Overflow and Underflow

### Overflow 

Overflow occurs when the result of an operation, such as addition or multiplication, exceeds the maximum representable value in the floating-point format. This means the value has become too large to be accurately represented with the available bits. Overflow can lead to inaccuracies in calculations and, in some cases, produce special "infinity" values or result in the loss of significant digits.

### Underflow 

Underflow, on the other hand, occurs when the result of an operation is smaller in magnitude than the smallest representable positive value (often called "denormal" or "subnormal" numbers).

![[Pasted image 20231014105417.png]]

---
