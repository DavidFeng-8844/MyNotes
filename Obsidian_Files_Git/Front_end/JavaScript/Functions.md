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