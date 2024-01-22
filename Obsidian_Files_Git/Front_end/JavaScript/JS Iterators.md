![[Pasted image 20231122212524.png]]The code above will log a nicely formatted list of the groceries to the console. Let’s explore the syntax of invoking `.forEach()`.

- `groceries.forEach()` calls the `forEach` method on the `groceries` array.
- `.forEach()` takes an argument of callback function. Remember, a callback function is a function passed as an argument into another function.
- `.forEach()` loops through the array and executes the callback function for each element. During each execution, the current element is passed as an argument to the callback function.
- The return value for `.forEach()` will always be `undefined`.

Another way to pass a callback for `.forEach()` is to use arrow function syntax.

```JavaScript
groceries.forEach(groceryItem => console.log(groceryItem));
```

We can also define a function beforehand to be used as the callback function.

```JavaScript
function printGrocery(element){  
	console.log(element);
}
groceries.forEach(printGrocery);
```

The above example uses a function declaration but you can also use a function expression or arrow function as well.

All three code snippets do the same thing. In each array iteration method, we can use any of the three examples to supply a callback function as an argument to the iterator. It’s good to be aware of the different ways to pass in callback functions as arguments in iterators because developers have different stylistic preferences. Nonetheless, due to the strong adoption of ES6, we will be using arrow function syntax in the later exercises.


## Call Back Functions

```JavaScript
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

Since, in JavaScript, functions are objects, functions can be passed as arguments.


### .map() method  
`.map()` works in a similar manner to `.forEach()`— the major difference is that `.map()` returns a new array.
In the example above:

- `numbers` is an array of numbers.
- `bigNumbers` will store the return value of calling `.map()` on `numbers`.
- `numbers.map` will iterate through each element in the `numbers` array and pass the element into the callback function.
- `return number * 10` is the code we wish to execute upon each element in the array. This will save each value from the `numbers` array, multiplied by `10`, to a new array.
```JavaScript
const numbers = [1, 2, 3, 4, 5];  
  
const bigNumbers = numbers.map(number => {  
  return number * 10;  
});
```

### .filter() Method 
Another useful iterator method is [`.filter()`](https://www.codecademy.com/resources/docs/javascript/arrays/filter?page_ref=catalog). Like `.map()`, `.filter()` returns a new array. However, `.filter()` returns an array of elements after filtering out certain elements from the original array. The callback function for the `.filter()` method should return `true` or `false` depending on the element that is passed to it. The elements that cause the callback function to return `true` are added to the new array. Take a look at the following example:
```JavaScript 
const words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door'];  
  
const shortWords = words.filter(word => {  
  return word.length < 6;  
});
```
- `words` is an array that contains string elements.
- `const shortWords =` declares a new variable that will store the returned array from invoking `.filter()`.
- The callback function is an arrow function that has a single parameter, `word`. Each element in the `words` array will be passed to this function as an argument.
- `word.length < 6;` is the condition in the callback function. Any `word` from the `words` array that has fewer than `6` characters will be added to the `shortWords` array.

### The .findIndex() Method

We sometimes want to find the location of an element in an array. That’s where the `.findIndex()` method comes in! Calling [`.findIndex()`](https://www.codecademy.com/resources/docs/javascript/arrays/findIndex?page_ref=catalog) on an array will return the index of the first element that evaluates to `true` in the callback function.

```JavaScript
const jumbledNums = [123, 25, 78, 5, 9]; 
const lessThanTen = jumbledNums.findIndex(num => {  return num < 10;});
```

- `jumbledNums` is an array that contains elements that are numbers.
- `const lessThanTen =` declares a new variable that stores the returned index number from invoking `.findIndex()`.
- The callback function is an arrow function that has a single parameter, `num`. Each element in the `jumbledNums` array will be passed to this function as an argument.
- `num < 10;` is the condition that elements are checked against. `.findIndex()` will return the index of the first element which evaluates to `true` for that condition.

Let’s take a look at what `lessThanTen` evaluates to:

```JavaScript
console.log(lessThanTen); // Output: 3 
```

If we check what element has index of 3:

```JavaScript
console.log(jumbledNums[3]); // Output: 5
```

Great, the element in index `3` is the number `5`. This makes sense since `5` is the first element that is less than 10.

If there isn’t a single element in the array that satisfies the condition in the callback, then `.findIndex()` will return `-1`.

```JavaScript
const greaterThan1000 = jumbledNums.findIndex(num => {  return num > 1000;});
console.log(greaterThan1000); // Output: -1
```

### The .reduce() Method

Another widely used iteration method is `.reduce()`. The [`.reduce()`](https://www.codecademy.com/resources/docs/javascript/arrays/reduce?page_ref=catalog) method returns a single value after iterating through the elements of an array, thereby _reducing_ the array. Take a look at the example below:

```JavaScript
const numbers = [1, 2, 4, 10];
const summedNums = numbers.reduce((accumulator, currentValue) => {  return accumulator + currentValue})
console.log(summedNums) // Output: 17
```

Here are the values of `accumulator` and `currentValue` as we iterate through the `numbers` array:

|Iteration|`accumulator`|`currentValue`|return value|
|---|---|---|---|
|First|1|2|3|
|Second|3|4|7|
|Third|7|10|17|

  

Now let’s go over the use of `.reduce()` from the example above:

- `numbers` is an array that contains numbers.
- `summedNums` is a variable that stores the returned value of invoking `.reduce()` on `numbers`.
- `numbers.reduce()` calls the `.reduce()` method on the `numbers` array and takes in a callback function as argument.
- The callback function has two parameters, `accumulator` and `currentValue`. The value of `accumulator` starts off as the value of the first element in the array and the `currentValue` starts as the second element. To see the value of `accumulator` and `currentValue` change, review the chart above.
- As `.reduce()` iterates through the array, the return value of the callback function becomes the `accumulator` value for the next iteration, `currentValue` takes on the value of the current element in the looping process.

The `.reduce()` method can also take an optional second parameter to set an initial value for `accumulator` (remember, the first argument is the callback function!). For instance:

```JavaScript
const numbers = [1, 2, 4, 10];
const summedNums = numbers.reduce((accumulator, currentValue) => {  return accumulator + currentValue}, 100)  // <- Second argument for .reduce()
console.log(summedNums); // Output: 117
```

Here’s an updated chart that accounts for the second argument of `100`:

|Iteration #|`accumulator`|`currentValue`|return value|
|---|---|---|---|
|First|100|1|101|
|Second|101|2|103|
|Third|103|4|107|
|Fourth|107|10|117|### Iterator Documentation

There are many additional built-in array methods, a complete list of which is on the [MDN’s Array iteration methods page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Iteration_methods).

The documentation for each method contains several sections:

1. A short definition.
2. A block with the correct syntax for using the method.
3. A list of parameters the method accepts or requires.
4. The return value of the function.
5. An extended description.
6. Examples of the method’s use.
7. Other additional information.

In the instructions below, there are some errors in the code. Use the documentation for a given method to determine the error or fill in a blank to make the code run correctly

### Review

Awesome job on clearing the iterators lesson! You have learned a number of useful methods in this lesson as well as how to use the JavaScript documentation from the Mozilla Developer Network to discover and understand additional methods. Let’s review!

- `.forEach()` is used to execute the same code on every element in an array but does not change the array and returns `undefined`.
- `.map()` executes the same code on every element in an array and returns a new array with the updated elements.
- `.filter()` checks every element in an array to see if it meets certain criteria and returns a new array with the elements that return truthy for the criteria.
- `.findIndex()` returns the index of the first element of an array that satisfies a condition in the callback function. It returns `-1` if none of the elements in the array satisfies the condition.
- `.reduce()` iterates through an array and takes the values of the elements and returns a single value.
- All iterator methods take a callback function, which can be a pre-defined function, a function expression, or an arrow function.
- You can visit the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) to learn more about iterator methods (and all other parts of JavaScript!).

---
### Review

Congratulations on finishing Advanced Objects!

Let’s review the concepts covered in this lesson:

- The object that a method belongs to is called the _calling object_.
- The `this` keyword refers to the calling object and can be used to access properties of the calling object.
- Methods do not automatically have access to other internal properties of the calling object.
- The value of `this` depends on where the `this` is being accessed from.
- We cannot use arrow functions as methods if we want to access other internal properties.
- JavaScript objects do not have built-in privacy, rather there are conventions to follow to notify other developers about the intent of the code.
- The usage of an underscore before a property name means that the original developer did not intend for that property to be directly changed.
- Setters and getter methods allow for more detailed ways of accessing and assigning properties.
- Factory functions allow us to create object instances quickly and repeatedly.
- There are different ways to use object destructuring: one way is the property value shorthand and another is destructured assignment.
- As with any concept, it is a good skill to learn how to use the documentation with objects!

You’re ready to start leveraging more elegant code for creating and accessing objects in your code!

### Instructions

If you want to challenge yourself:

- Find the value of `this` in a function inside of a method.
- Learn the outcome of using a property that has the exact same name as a setter/getter method.
- Create a new factory function that can create object instances of your choice.
- Read documentation on other destructuring techniques and apply it to your code.
- Try out other built-in object methods and learn what they do.