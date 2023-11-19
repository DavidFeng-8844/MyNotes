### Dot Notation for Accessing Object Properties

Properties of a JavaScript object can be accessed using the dot notation in this manner: `object.propertyName`. Nested properties of an object can be accessed by chaining key names in the correct order.

```JavaScript
const apple = { 

  color: 'Green',

  price: {

    bulk: '$3/kg',

    smallQty: '$4/kg'

  }

};

console.log(apple.color); // 'Green'

console.log(apple.price.bulk); // '$3/kg'
```

## Objects passed as arguments
They are passed by _reference_, not by value. This means that the object itself (not a copy) is accessible and mutable (can be changed) inside that function.

```JavaScript
const origNum = 8;

const origObj = {color: 'blue'};

const changeItUp = (num, obj) => {

  num = 7;

  obj.color = 'red';

};

changeItUp(origNum, origObj);

// Will output 8 since integers are passed by value.

console.log(origNum);

// Will output 'red' since objects are passed 

// by reference and are therefore mutable.

console.log(origObj.color);
```