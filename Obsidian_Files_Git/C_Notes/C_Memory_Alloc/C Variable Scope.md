Pocus is an external variable known to magic() but not to main() because Pocus
follows main() .
```c
/* Example 3 */
int Hocus;
int magic();
int main(void)
{
int Hocus; // Hocus declared, is auto by default
...
}
int Pocus;
int magic()
{
auto int Hocus; // local Hocus declared automatic
}
```

>Unlike automatic variables, <mark style="background: #ABF7F7A6;">external variables are initialized automatically to zero</mark> if you don’t initialize them. 

Unlike the case for automatic variables,
you can use only constant expressions to initialize file scope variables:
```c
int x = 10; // ok, 10 is constant
int y = 3 + 20; // ok, a constant expression
size_t z = sizeof(int); // ok, a constant expression
int x2 = 2 * x; // not ok, x is a variable
```
(As long as the type is not a variable array, a sizeof expression is considered a constant expression.)


---
When a variable is declared external to any function in a file, it’s an external variable and has
file scope, external linkage, and static storage duration. If you add the keyword static to such
a declaration, you get a variable with static storage duration, file scope, and internal linkage.
If you declare a variable inside a function and use the keyword static , the variable has static
storage duration, block scope, and no linkage.