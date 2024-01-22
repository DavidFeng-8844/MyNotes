
```JavaScript
let x = 5;
let y = "Hello";
let z = true;
let w;

console.log(typeof x); // Outputs: "number"
console.log(typeof y); // Outputs: "string"
console.log(typeof z); // Outputs: "boolean"
console.log(typeof w); // Outputs: "undefined"
console.log(typeof null); // Outputs: "object" (typeof null is an historical bug in JavaScript, as null is not an object)
console.log(typeof [1, 2, 3]); // Outputs: "object" (arrays are objects)
console.log(typeof { key: "value" }); // Outputs: "object" (objects are objects)
console.log(typeof function() {}); // Outputs: "function"

```

ATTENTION typeof returns in string so when comparing always add ""

```JavaScript
const robot = {

  _model: '1E78V2',

  _energyLevel: 100,

  get energyLevel() {

    if(typeof(this._energyLevel) === "number") {

      return `My current energy level is ${this._energyLevel}`;

    }

  }

};
```