### jQuery Library

We are going to use jQuery to add some interactivity to the MOVE Gear site, an online marketplace for athletic apparel.

To use the jQuery library, **index.html** must load it with the other dependencies. Take a look at the attached diagram to see where various dependencies load in an HTML document.

The document is loaded from top to bottom. So the style dependencies in the `<head>` will load first, then the structural elements in the `<body>` will load next. It has become common practice to link the main JavaScript file at the bottom of the HTML document because a good deal of the content of the script will require that the dependencies, style sheets and elements exist before the browser can run the JavaScript that uses and references those things.

When you add the jQuery library to your project in the next exercise, you will do so on the line before the `</body>` tag. Because HTML files load from top to bottom, adding the jQuery library at the bottom of your project will ensure that it will not affect the HTML (structure) and CSS (style) load times.

![[Pasted image 20231217230756.png]]

### Adding Jquery 

To include jQuery, we use a `<script>` tag as follows:

```JavaScript 
<script
src="https://code.jquery.com/jquery-3.2.1.min.js"  
integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4="  
crossorigin="anonymous"></script>
```
We will use jQuery methods in a JavaScript file called **main.js**, which we will load into **index.html** using a `<script>` tag. We need to load the jQuery library before the **main.js** file. Otherwise, the computer will not understand the jQuery used in **main.js**.

>Newer Version 

```Javascript
<script src="https://code.jquery.com/jquery-3.7.1.min.js" integrity="sha256-/JqT3SQfawRcv/BIHPThkBvs0OEvtFFmqPF/lYI/Cxo=" crossorigin="anonymous"></script>
```

> Other Version on the Official Website 
> [jQuery CDN](https://releases.jquery.com/)

### .ready()
The jQuery `.ready()` method waits until the HTML page’s DOM is ready to manipulate. You should wrap all JavaScript behavior inside of the `.ready()` method. This will make sure the web page is rendered in the browser before any jQuery code executes.

```JavaScript 
$(document).ready(() => {});
```
## Targeting by class 

We can use the same `$()` syntax to create jQuery [objects](https://www.codecademy.com/resources/docs/javascript/objects) for elements on a web page. Typically, we pass a string into `$()` to target elements by id, class, or tag. Once targeted, we can use `.` notation to attach a handler method that triggers a callback function.

```Javascript 
$('.someClass').handlerMethod();
```
### Targeting by id

While classes allow us to target multiple elements at once, we can also target single elements by `id`.

To select by `id`, we prepend the element’s id name with the `#` symbol.

```JavaScript 
$('#someId').hide();
```

### jQuery Objects

Now that you’ve seen some [jQuery](https://www.codecademy.com/resources/docs/javascript/jquery) in action, let’s dive a bit deeper into syntax. You’ve probably noticed the `$` symbol before anything we target. The `$` symbol is an alias for the `jQuery` function. The `$` symbol and `jQuery` are interchangeable.

The `jQuery` function takes a parameter that targets an element, like `'#navMenu'`, and turns it into a jQuery object. Then, you can call any jQuery method on a jQuery object.

Developers often save jQuery [objects](https://www.codecademy.com/resources/docs/javascript/objects) in [variables](https://www.codecademy.com/resources/docs/javascript/variables), like so:

```JavaScript 
const $jQueryObject = $('.someClass');
```
### Event Handlers

Now that we’ve got jQuery up and running, let’s give it a little gas! The jQuery `.on()` method adds event handlers to jQuery [objects](https://www.codecademy.com/resources/docs/javascript/objects). The method takes two parameters: a string declaring the event to listen for (the handler) and a callback function to fire when the event is detected.

```JavaScript 
$('#login').on('click', () => {  $loginForm.show();})
```
