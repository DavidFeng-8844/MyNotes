### The Document Keyword

The _Document Object Model_, abbreviated DOM, is a powerful tree-like structure that organizes the elements on a web page and allows scripting languages to access them. This lesson will focus on some of the most useful methods and properties of the [DOM interface](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) in JavaScript. This interface is implemented by every modern browser.

First things first! The `document` object in JavaScript is the door to the DOM structure. The `document` object allows you to access the root node of the DOM tree. Before you can access a specific element in the page, first you must access the document structure itself. The `document` object allows scripts to access children of the DOM as properties.

For example, if you want to access the `<body>` element from your script, you can access it as a property of the `document` object by using `document.body`. This property will return the body element of that DOM.

Similarly, you could access the `<title>` element with the `.title` property. Here is a [comprehensive list](https://developer.mozilla.org/en-US/docs/Web/API/Document) of all `document` properties.

### Tweak an Element

When using the DOM in your script to access an HTML element, whether it’s an `<li>` element or the entire `<body>` element, you also have access to all of that element’s properties.

This includes the ability to modify the contents of the element as well as its attributes and properties, which can range from modifying the text inside a `<p>` element to assigning a new background color to a `<div>`. For example, the `.innerHTML` property allows you to access and set the contents of an element.

Let’s take a look at how we can reassign the contents of the `<body>` element to the text `'The cat loves the dog'`:

```JavaScript
document.body.innerHTML = 'The cat loves the dog.';
```

The `.innerHTML` property can also add any valid HTML elements. The following example replaces the contents of the `<body>` element by assigning an `<h2>` element as a child inside the `<body>` element:

```JavaScript
document.body.innerHTML = '<h2>This is a heading</h2>';

```

### Select and Modify Elements

In the previous exercise, we accessed the `<body>` element with the `document` keyword!

What if we wanted to select a specific element besides the entire `<body>` element? The DOM interface allows us to access a specific element with CSS selectors.

_CSS selectors_ define the elements to which a set of CSS rules apply, but we can also use these same selectors to access DOM elements with JavaScript! Selectors can include a tag name, a class, or an ID.

<mark style="background: #ABF7F7A6;">The `.querySelector()` method allows us to specify a CSS selector as a string and returns the first element that matches that selector. </mark>The following code would return the first paragraph in the document.

```JavaScript
document.querySelector('p');
```

Along with `.querySelector()`, JavaScript has more targeted methods that select elements based on their class, id, or tag name.

For example, if you want to <mark style="background: #ABF7F7A6;">access an element directly by its `id`, you can use the aptly named `.getElementById()` method:</mark>

```JavaScript
document.getElementById('bio').innerHTML = 'The description';
```

In this example, we’ve selected the element with an ID of `'bio'` and set its `.innerHTML` to the text `'The description'`. Notice that the ID is passed as a string, wrapped in quotation marks (`' '`).

There are also the `.getElementsByClassName()` and `.getElementsByTagName()` methods which return an array of elements, instead of just one element. You can use bracket notation to access individual elements of an array:

```JavaScript
// Set first element of .student class as 'Not yet registered'
document.getElementsByClassName('student')[0].innerHTML = 'Not yet registered';
// Set second <li> tag as 'Cedric Diggory'
document.getElementsByTagName('li')[1].innerHTML = 'Cedric Diggory`;
```

In the above example code, the first element with the `'student'` class and the second `<li>` element have had their inner HTML changed.


### Review

In this lesson, you manipulated a webpage structure by leveraging the Document Object Model (DOM) interface in JavaScript.

Let’s review what we learned:

- The `document` keyword grants access to the root of the DOM in JavaScript.
- The DOM Interface allows you to select a specific element with CSS selectors by using the `.querySelector()` method.
- You can access an element ==directly== by its ID with the `.getElementById()` method which returns a single element.
- You can access an array of elements with the `.getElementsByClassName()` and `.getElementsByTagName()` methods, then call a single element by referencing its placement in the array.
- The `.innerHTML` and `.style` properties allow you to modify an element by changing its contents or style respectively.
- You can create, append, and remove elements by using the `.createElement()`,`.appendChild()` and `.removeChild()` methods respectively.
- The `.onclick` property can add interactivity to a DOM element based on a click event.
- The `.children` property returns a list of an element’s children and the `.parentNode` property returns the element’s closest connected node in the direction towards the root.


## Examples

> BackGround Color using style 

```JavaScript 
document.getElementById('gears-container').style.backgroundColor = 'red';
```