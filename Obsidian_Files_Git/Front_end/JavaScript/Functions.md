## Initialize a function
![[Pasted image 20231120102227.png]]
## Default Parameters
```javaScript
function greeting (name = 'stranger') { console.log(`Hello, ${name}!`) } greeting('Nick') // Output: Hello, Nick! greeting() // Output: Hello, stranger!
```
## Call back Functions 

```Javascript
const isEven = (n) => {

  return n % 2 == 0;

}

let printMsg = (evenFunc, num) => {

  const isNumEven = evenFunc(num);

  console.log(`The number ${num} is an even number: ${isNumEven}.`)

}

// Pass in isEven as the callback function

printMsg(isEven, 4); 

// Prints: The number 4 is an even number: True.
```

In JavaScript, a callback function is a function that is passed into another function as an argument.

## Higher Order Functions
A “higher-order function” is a function that accepts functions as parameters and/or returns a function.

## Function Expressions 

Another way to define a function is to use a _function expression_. To define a function inside an expression, we can use the `function` keyword. In a function expression, the function name is usually omitted. A function with no name is called an _anonymous function_. A function expression is often stored in a variable in order to refer to it.
![[Pasted image 20231120112638.png]]

## Arrow Functions 
[Arrow functions](https://www.codecademy.com/resources/docs/javascript/arrow-functions?page_ref=catalog) remove the need to type out the keyword `function` every time you need to create a function. Instead, you first include the parameters inside the `( )` and then add an arrow `=>` that points to the function body surrounded in `{ }` like this:
```JavaScript
const rectangleArea = (width, height) => {  
  let area = width * height;  
  return area;  
};
```

## Concise Body Arrow Functions

1. Functions that take only a single parameter do not need that parameter to be enclosed in parentheses. However, if a function takes zero or multiple parameters, parentheses are required.
	![[Pasted image 20231120121052.png]]
2.  A function body composed of a ==single-line block== does not need curly braces. Without the curly braces, whatever that line evaluates will be automatically returned. The contents of the block should immediately follow the arrow `=>` and the `return` keyword can be removed. This is referred to as _implicit return_.
	![[Pasted image 20231120121355.png]]