### Creating Object Literals

Objects can be assigned to variables just like any JavaScript type. We use curly braces, `{}`, to designate an _object literal_:

```
let spaceship = {}; // spaceship is an empty object
```

We fill an object with unordered data. This data is organized into ==key-value pairs==. A key is like a variable name that points to a location in memory that holds a value.


A key’s value can be of any data type in the language including functions or other objects.

We make a key-value pair by writing the key’s name, or _identifier_, followed by a colon and then the value. We separate each key-value pair in an object literal with a comma (`,`). Keys are strings, but when we have a key that does not have any special characters in it, JavaScript allows us to omit the quotation marks:
```JavaScript
// An object literal with two key-value pairslet 
spaceship = {  'Fuel Type': 'diesel',  color: 'silver'};
```

The `spaceship` object has two properties `Fuel Type` and `color`. `'Fuel Type'` has quotation marks because it contains a space character.

Let’s make some objects!


### Accessing Properties

There are two ways we can access an object’s property. Let’s explore the first way— dot notation, `.`.

You’ve used dot notation to access the properties and methods of built-in objects and data instances:

```JavaScript
'hello'.length; // Returns 5
```

With property dot notation, we write the object’s name, followed by the dot operator and then the property name (key):

```JavaScript
let spaceship = {  homePlanet: 'Earth',  color: 'silver'};spaceship.homePlanet; // Returns 'Earth',spaceship.color; // Returns 'silver',
```

![](https://content.codecademy.com/courses/learn-javascript-objects/object%20dot%20notation.svg)

If we try to access a property that does not exist on that object, `undefined` will be returned.

```JavaScript
spaceship.favoriteIcecream; // Returns undefined
```

### Bracket Notation

The second way to access a key’s value is by using bracket notation, `[ ]`.

You’ve used bracket notation when indexing an array:

```JavaScript
['A', 'B', 'C'][0]; // Returns 'A'
```

To use bracket notation to access an object’s property, we pass in the property name (key) as a string.


We ==**must** use bracket notation when accessing keys that have numbers, spaces, or special characters in them. Without bracket notation in these situations, our code would throw an error.==

```JavaScript 
let spaceship = {
	'Fuel Type': 'Turbo Fuel',
	'Active Duty': true,
	homePlanet: 'Earth',
	numCrew: 5
	};
	spaceship['Active Duty'];// Returns true
	spaceship['Fuel Type'];   // Returns  'Turbo Fuel'
	spaceship['numCrew'];   // Returns 5
	spaceship['!!!!!!!!!!!!!!!'];   // Returns undefined

```

With bracket notation you can also use a variable inside the brackets to select the keys of an object. This can be especially helpful when working with functions:

```JavaScript
let returnAnyProp = (objectName, propName) => objectName[propName]; returnAnyProp(spaceship, 'homePlanet'); // Returns 'Earth'
```

==If we tried to write our `returnAnyProp()` function with dot notation (`objectName.propName`) the computer would look for a key of `'propName'` on our object and not the value of the `propName` parameter.==

Let’s get some practice using bracket notation to access properties!

### Property Assignment

Once we’ve defined an object, we’re not stuck with all the properties we wrote. Objects are _mutable_ meaning we can update them after we create them!

We can use either dot notation, `.`, or bracket notation, `[]`, and the assignment operator, `=` to add new key-value pairs to an object or change an existing property.

![diagram showing how an object followed by brackets ([]) with the property name as a string can be reassigned to a new value. This same idea applies for accessing a property using dot notation which has the object name, followed by a dot and the name of the property](https://static-assets.codecademy.com/Courses/Learn-JavaScript/objects/object_property_assignment.svg)

One of two things can happen with property assignment:

- If the property already exists on the object, whatever value it held before will be replaced with the newly assigned value.
- If there was no property with that name, a new property will be added to the object.

It’s important to know that although we can’t reassign an object declared with `const`, we can still mutate it, meaning we can add new properties and change the properties that are there.

```JavaScript
const spaceship = {type: 'shuttle'};
spaceship = {type: 'alien'}; // TypeError: Assignment to
constant variable.spaceship.type = 'alien'; // Changes the value of the type
propertyspaceship.speed = 'Mach 5'; // Creates a new key of 'speed' with a value of 'Mach 5'
```

You can delete a property from an object with the `delete` operator.

```JavaScript
const spaceship = {  
  'Fuel Type': 'Turbo Fuel',  
  homePlanet: 'Earth',  
  mission: 'Explore the universe'  
};  
  
delete spaceship.mission;  // Removes the mission property
```
### Methods

==When the data stored on an object is a function we call that a [_method_](https://www.codecademy.com/resources/docs/javascript/methods?page_ref=catalog). ==A property is what an object has, while a method is what an object does.

Do object methods seem familiar? That’s because you’ve been using them all along! For example `console` is a global JavaScript object and `.log()` is a method on that object. `Math` is also a global JavaScript object and `.floor()` is a method on it.

We can include methods in our object literals by creating ordinary, colon-separated key-value pairs. The key serves as our method’s name, while the value is an anonymous function expression.

```JavaScript
const alienShip = {  
invade: function () { 
   console.log('Hello! We have come to dominate your planet.    Instead of Earth, it shall be called New Xaculon.')  
}};
```

With the new method syntax introduced in ES6 we can omit the colon and the `function` keyword.

```javascript
const alienShip = {  invade () {     console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')  }};
```

Object methods are invoked by appending the object’s name with the dot operator followed by the method name and parentheses:

```javascript
alienShip.invade(); // Prints 'Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.'
```

### Nested Objects

In application code, objects are often nested— an object might have another object as a property which in turn could have a property that’s an array of even more objects!

In our `spaceship` object, we want a `crew` object. This will contain all the crew members who do important work on the craft. Each of those `crew` members are objects themselves. They have properties like `name`, and `degree`, and they each have unique methods based on their roles. We can also nest other objects in the `spaceship` such as a `telescope` or nest details about the spaceship’s computers inside a parent `nanoelectronics` object.

```JavaScript
const spaceship = {  
     telescope: {  
        yearBuilt: 2018,  
        model: '91031-XLT',  
        focalLength: 2032  
     },  
    crew: {  
        captain: {   
            name: 'Sandra',  
            degree: 'Computer Engineering',  
            encourageTeam() { console.log('We got this!') }   
         }  
    },  
    engine: {  
        model: 'Nimbus2000'  
     },  
     nanoelectronics: {  
         computer: {  
            terabytes: 100,  
            monitors: 'HD'  
         },  
        'back-up': {  
           battery: 'Lithium',  
           terabytes: 50  
         }  
    }  
};
```

We can chain operators to access nested properties. We’ll have to pay attention to which operator makes sense to use in each layer. It can be helpful to pretend you are the computer and evaluate each expression from left to right so that each operation starts to feel a little more manageable.

```JavaScript 
spaceship.nanoelectronics['back-up'].battery; // Returns 'Lithium'
```

In the preceding code:

- First the computer evaluates `spaceship.nanoelectronics`, which results in an object containing the `back-up` and `computer` objects.
- We accessed the `back-up` object by appending `['back-up']`.
- The `back-up` object has a `battery` property, accessed with `.battery` which returned the value stored there: `'Lithium'`
### Pass By Reference

Objects are _passed by reference_. This means when we pass a variable assigned to an object into a function as an argument, the computer interprets the parameter name as pointing to the space in memory holding that object. As a result, functions which change object properties actually mutate the object permanently (even when the object is assigned to a `const` variable).

```JavaScript
const spaceship = {  
  homePlanet : 'Earth',  
  color : 'silver'  
};  
  
let paintIt = obj => {  
  obj.color = 'glorious gold'  
};  
  
paintIt(spaceship);  
  
spaceship.color // Returns 'glorious gold'
```

Our function `paintIt()` permanently changed the color of our `spaceship` object. However, reassignment of the `spaceship` variable wouldn’t work in the same way:

```JavaScript
let spaceship = {  
  homePlanet : 'Earth',  
  color : 'red'  
};  
let tryReassignment = obj => {  
  obj = {  
    identified : false,  
    'transport type' : 'flying'  
  }  
  console.log(obj) // Prints {'identified': false, 'transport type': 'flying'}  
  
};  
tryReassignment(spaceship) // The attempt at reassignment does not work.  
spaceship // Still returns {homePlanet : 'Earth', color : 'red'};  
  
spaceship = {  
  identified : false,  
  'transport type': 'flying'  
}; // Regular reassignment still works.
```

Let’s look at what happened in the code example:

- We declared this `spaceship` object with `let`. This allowed us to reassign it to a new object with `identified` and `'transport type'` properties with no problems.
- When we tried the same thing using a function designed to reassign the object passed into it, the reassignment didn’t stick (even though calling `console.log()` on the object produced the expected result).
- When we passed `spaceship` into that function, `obj` became a reference to the memory location of the `spaceship` object, but _not_ to the `spaceship` variable. This is because the `obj` parameter of the `tryReassignment()` function is a variable in its own right. The body of `tryReassignment()` has no knowledge of the `spaceship` variable at all!
- When we did the reassignment in the body of `tryReassignment()`, the `obj` variable came to refer to the memory location of the object `{'identified' : false, 'transport type' : 'flying'}`, while the `spaceship` variable was completely unchanged from its
### Looping Through Objects

Loops are programming tools that repeat a block of code until a condition is met. We learned how to iterate through arrays using their numerical indexing, but the key-value pairs in objects aren’t ordered! [JavaScript has given us alternative solution for iterating through objects with the `for...in` syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) .

`for...in` will execute a given block of code for each property in an object.

```JavaScript
let spaceship = {  
  crew: {  
    captain: {   
      name: 'Lily',  
      degree: 'Computer Engineering',  
      cheerTeam() { console.log('You got this!') }   
    },  
    'chief officer': {   
      name: 'Dan',  
      degree: 'Aerospace Engineering',  
      agree() { console.log('I agree, captain!') }   
    },  
    medic: {   
      name: 'Clementine',  
      degree: 'Physics',  
      announce() { console.log(`Jets on!`) } },  
    translator: {  
      name: 'Shauna',  
      degree: 'Conservation Science',  
      powerFuel() { console.log('The tank is full!') }   
    }  
  }  
};  
  
// for...in  
for (let crewMember in spaceship.crew) {  
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);  
}
```

Our `for...in` will iterate through each element of the `spaceship.crew` object. In each iteration, the variable `crewMember` is set to one of `spaceship.crew`‘s keys, enabling us to log a list of crew members’ role and `name`.


### Review

Way to go! You’re well on your way to understanding the mechanics of objects in JavaScript. By building your own objects, you will have a better understanding of how JavaScript built-in objects work as well. You can also start imagining organizing your code into objects and modeling real world things in code.

Let’s review what we learned in this lesson:

- Objects store collections of _key-value_ pairs.
- Each key-value pair is a property—when a property is a function it is known as a method.
- An object literal is composed of comma-separated key-value pairs surrounded by curly braces.
- You can access, add or edit a property within an object by using dot notation or bracket notation.
- We can add methods to our object literals using key-value syntax with anonymous function expressions as values or by using the new ES6 method syntax.
- We can navigate complex, nested objects by chaining operators.
- Objects are mutable—we can change their properties even when they’re declared with `const`.
- Objects are passed by reference— when we make changes to an object passed into a function, those changes are permanent.
- We can iterate through objects using the `For...in` syntax.

---
# Advanced Objects 

### The this Keyword

Objects are collections of related data and functionality. We store that functionality in methods on our objects:

```JavaScript
const goat = {  
  dietType: 'herbivore',  
  makeSound() {  
    console.log('baaa');  
  }  
};
```

In our `goat` object we have a `.makeSound()` method. We can invoke the `.makeSound()` method on `goat`.

```JavaScript
goat.makeSound(); // Prints baaa
```

Nice, we have a `goat` object that can print `baaa` to the console. Everything seems to be working fine. What if we wanted to add a new method to our `goat` object called `.diet()` that prints the `goat`‘s `dietType`?

```JavaScript
const goat = {  
  dietType: 'herbivore',  
  makeSound() {  
    console.log('baaa');  
  },  
  diet() {  
    console.log(dietType);  
	  }  
};  
goat.diet();  
// Output will be "ReferenceError: dietType is not defined"
```

That’s strange, why is `dietType` not defined even though it’s a property of `goat`? That’s because inside the scope of the `.diet()` method, we don’t automatically have access to other properties of the `goat` object.

Here’s where the [`this`](https://www.codecademy.com/resources/docs/javascript/this?page_ref=catalog) keyword comes to the rescue. ==If we change the `.diet()` method to use the `this`, the `.diet()` works! :==

```JavaScript
const goat = {  
  dietType: 'herbivore',  
  makeSound() {  
    console.log('baaa');  
  },  
  diet() {  
    console.log(this.dietType);  
  }  
};  
  
goat.diet();  
// Output: herbivore
```

The `this` keyword references the _calling object_ which provides access to the calling object’s properties. In the example above, the calling object is `goat` and by using `this` we’re accessing the `goat` object itself, and then the `dietType` property of `goat` by using property dot notation.

Let’s get comfortable using the `this` keyword in a method.

### Arrow Functions and this

We saw in the previous exercise that for a method, the calling object is the object the method belongs to. If we use the [`this`](https://www.codecademy.com/resources/docs/javascript/this?page_ref=catalog) keyword in a method then the value of `this` is the calling object. However, it becomes a bit more complicated when we start using arrow functions for methods. Take a look at the example below:

```JavaScript
const goat = {  
  dietType: 'herbivore',  
  makeSound() {  
    console.log('baaa');  
  },  
  diet: () => {  
    console.log(this.dietType);  
  }  
};  
  
goat.diet(); // Prints undefined
```

In the comment, you can see that `goat.diet()` would log `undefined`. So what happened? Notice that the `.diet()` method is defined using an arrow function.

Arrow functions inherently _bind_, or tie, an already defined `this` value to the function itself that is NOT the calling object. In the code snippet above, the value of `this` is the _global object_, or an object that exists in the global scope, which doesn’t have a `dietType` property and therefore returns `undefined`.

To read more about either arrow functions or the global object check out the MDN documentation of [the global object](https://developer.mozilla.org/en-US/docs/Glossary/Global_object) and [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions).

The key takeaway from the example above is to _avoid_ using arrow functions when using `this` in a method!

### Privacy

Accessing and updating properties is fundamental in working with objects. However, there are cases in which we don’t want other code simply accessing and updating an object’s properties. When discussing _privacy_ in objects, we define it as the idea that only certain properties should be mutable or able to change in value.

Certain languages have privacy built-in for objects, but JavaScript does not have this feature. Rather, JavaScript developers follow naming conventions that signal to other developers how to interact with a property. One common convention is to place an underscore `_` before the name of a property to mean that the property should not be altered. Here’s an example of using `_` to prepend a property.

```JavaScript
const bankAccount = {  _amount: 1000}
```

In the example above, the `_amount` is not intended to be directly manipulated.

Even so, it is still possible to reassign `_amount`:

```JavaScript
bankAccount._amount = 1000000;
```

In later exercises, we’ll cover the use of methods called _getters_ and _setters_. Both methods are used to respect the intention of properties prepended, or began, with `_`. Getters can return the value of internal properties and setters can safely reassign property values. For now, let’s see what happens if we can change properties that don’t have setters or getters.

### Getters

_Getters_ are methods that get and return the internal properties of an object. But they can do more than just retrieve the value of a property! Let’s take a look at a getter method:

```JavaScript
const person = {  
  _firstName: 'John',  
  _lastName: 'Doe',  
  get fullName() {  
    if (this._firstName && this._lastName){  
      return `${this._firstName} ${this._lastName}`;  
    } else {  
      return 'Missing a first name or a last name.';  
    }  
  }  
}  
  
// To call the getter method:  
person.fullName; // 'John Doe'
```

Notice that in the getter method above:

- We use the `get` keyword followed by a function.
- We use an `if...else` conditional to check if both `_firstName` and `_lastName` exist (by making sure they both return truthy values) and then return a different value depending on the result.
- We can access the calling object’s internal properties using `this`. In `fullName`, we’re accessing both `this._firstName` and `this._lastName`.
- In the last line we call `fullName` on `person`. ==In general, getter methods do not need to be called with a set of parentheses. Syntactically, it looks like we’re accessing a property.==

Now that we’ve gone over syntax, let’s discuss some notable advantages of using getter methods:

- Getters can perform an action on the data when getting a property.
- Getters can return different values using conditionals.
- In a getter, we can access the properties of the calling object using `this`.
- The functionality of our code is easier for other developers to understand.

Another thing to keep in mind when using getter (and setter) methods is that properties cannot share the same name as the getter/setter function. If we do so, then calling the method will result in an infinite call stack error. One workaround is to add an underscore before the property name like we did in the example above.

Great, let’s go getter!

### Setters

Along with getter methods, we can also create _setter_ methods which reassign values of existing properties within an object. Let’s see an example of a setter method:

```JavaScript
const person = {  
  _age: 37,  
  set age(newAge){  
    if (typeof newAge === 'number'){  
      this._age = newAge;  
    } else {  
      console.log('You must assign a number to age');  
    }  
  }  
};
```

Notice that in the example above:

- We can perform a check for what value is being assigned to `this._age`.
- When we use the setter method, only values that are numbers will reassign `this._age`
- There are different outputs depending on what values are used to reassign `this._age`.

Then to use the setter method:

```JavaScript
person.age = 40;  
console.log(person._age); // Logs: 40  
person.age = '40'; // Logs: You must assign a number to age
```

Setter methods like `age` do not need to be called with a set of parentheses. Syntactically, it looks like we’re reassigning the value of a property.

Like getter methods, there are similar advantages to using setter methods that include checking input, performing actions on properties, and displaying a clear intention for how the object is supposed to be used. Nonetheless, even with a setter method, it is still possible to directly reassign properties. For example, in the example above, we can still set `._age` directly:

```JavaScript
person._age = 'forty-five'
console.log(person._age); // Prints forty-five
```

### Factory Functions

So far we’ve been creating objects individually, but there are times where we want to create many instances of an object quickly. Here’s where _factory functions_ come in. A real world factory manufactures multiple copies of an item quickly and on a massive scale. A factory function is a function that returns an object and can be reused to make multiple object instances. Factory functions can also have parameters allowing us to customize the object that gets returned.

Let’s say we wanted to create an object to represent monsters in JavaScript. There are many different types of monsters and we could go about making each monster individually but we can also use a factory function to make our lives easier. To achieve this diabolical plan of creating multiple monsters objects, we can use a factory function that has parameters:

```JavaScript
const monsterFactory = (name, age, energySource, catchPhrase) => {  
  return {   
    name: name,  
    age: age,  
    energySource: energySource,  
    scare() {  
      console.log(catchPhrase);  
    }  
  }  
};
```

In the `monsterFactory` function above, it has four parameters and returns an object that has the properties: `name`, `age`, `energySource`, and `scare()`. To make an object that represents a specific monster like a ghost, we can call `monsterFactory` with the necessary arguments and assign the return value to a variable:

```JavaScript
const ghost = monsterFactory('Ghouly', 251, 'ectoplasm', 'BOO!');  
ghost.scare(); // 'BOO!'
```

Now we have a `ghost` object as a result of calling `monsterFactory()` with the needed arguments. With `monsterFactory` in place, we don’t have to create an object literal every time we need a new monster. Instead, we can invoke the `monsterFactory` function with the necessary arguments to ~~take over the world~~ make a monster for us!

### Property Value Shorthand

ES6 introduced some new shortcuts for assigning properties to variables known as _destructuring_.

In the previous exercise, we created a factory function that helped us create objects. We had to assign each property a key and value even though the key name was the same as the parameter name we assigned to it. To remind ourselves, here’s a truncated version of the factory function:

```JavaScript
const monsterFactory = (name, age) => {  
  return {   
    name: name,  
    age: age  
  }  
};
```

Imagine if we had to include more properties, that process would quickly become tedious! But we can use a destructuring technique, called _property value shorthand_, to save ourselves some keystrokes. The example below works exactly like the example above:

```JavaScript
const monsterFactory = (name, age) => {  
  return {   
    name,  
    age  
  }  
};
```

Notice that we don’t have to repeat ourselves for property assignments!

### Destructured Assignment

We often want to extract key-value pairs from objects and save them as variables. Take for example the following object:

```JavaScript
const vampire = {  
  name: 'Dracula',  
  residence: 'Transylvania',  
  preferences: {  
    day: 'stay inside',  
    night: 'satisfy appetite'  
  }  
};
```

If we wanted to extract the `residence` property as a variable, we could use the following code:

```JavaScript
const residence = vampire.residence;  
console.log(residence); // Prints 'Transylvania'
```

However, we can also take advantage of a destructuring technique called ==_destructured assignment_== to save ourselves some keystrokes. In destructured assignment we create a variable with the name of an object’s key that is wrapped in curly braces `{ }` and assign to it the object. Take a look at the example below:

```JavaScript
const { residence } = vampire;  
console.log(residence); // Prints 'Transylvania'
```

Look back at the `vampire` object’s properties in the first code example. Then, in the example above, we declare a new variable `residence` that extracts the value of the `residence` property of `vampire`. When we log the value of `residence` to the console, `'Transylvania'` is printed.

We can even use destructured assignment to grab nested properties of an object:

```JavaScript
const { day } = vampire.preferences; 
console.log(day); // Prints 'stay inside'
```

> Since `functionality` is referencing `robot.functionality` we can call the methods available to `robot.functionality` simply through `functionality`.Take advantage of this shortcut and call the `.beep()` method on `functionality`.
    
```JavaScript
const robot = {

  model: '1E78V2',

  energyLevel: 100,

  functionality: {

    beep() {

      console.log('Beep Boop');

    },

    fireLaser() {

      console.log('Pew Pew');

    },

  }

};

  

const { functionality } = robot;
```


### Built-in Object Methods

In the previous exercises we’ve been creating instances of objects that have their own methods. But, we can also take advantage of built-in methods for Objects!

For example, we have access to object instance methods like: `.hasOwnProperty()`, `.valueOf()`, and many more! Practice your documentation reading skills and check out: [MDN’s object instance documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#Methods).

There are also useful Object class methods such as `Object.assign()`, `Object.entries()`, and `Object.keys()` just to name a few. For a comprehensive list, browse: [MDN’s object instance documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#Methods_of_the_Object_constructor).

Let’s get acquainted with some of these methods and their documentation.

Note: You will see errors as you work through this exercise, but by the end the errors will be fixed!


Example: 
# Object.keys()

The **`Object.keys()`** static method returns an array of a given object's own enumerable string-keyed property names.

```JavaScript
const object1 = {
  a: 'somestring',
  b: 42,
  c: false,
};

console.log(Object.keys(object1));
// Expected output: Array ["a", "b", "c"]
```