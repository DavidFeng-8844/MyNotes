<mark style="background: #ABF7F7A6;">N.B</mark>
>1. Change the CSS property of the `moreInfo` element from a display of `none` to `block`. To change a CSS property in JavaScript, you must use the following syntax:

```JavaScript 
element.style.property = 'value';
```


### Event Handler Registration

You’re doing great! Now it’s time to dive into using event handler functions to create interactivity.

Using the `.addEventListener()` method, we can have a DOM element listen for a specific event and execute a block of code when the event is detected. <mark style="background: #ABF7F7A6;">The DOM element that listens for an event is called the _event target_ and the block of code that runs when the event happens is called the _event handler_.</mark>

Let’s take a look at the code below:

```JavaScript 
let eventTarget = document.getElementById('targetElement');  
  
eventTarget.addEventListener('click', function() {  
  // this block of code will run when click event happens on eventTarget element  
});
```

Let’s break this down!

- We selected our event target from the DOM using `document.getElementById('targetElement')`.
- We used the `.addEventListener()` method on the `eventTarget` DOM element.
- The `.addEventListener()` method takes two arguments: an event name in _string_ format and an event handler function. We will learn about different values we can use as event names in a later lesson.
- In this example, we used the `'click'` event, which fires when the user clicks on `eventTarget`.
- The code block in the event handler function will execute when the `'click'` event is detected.

Instead of using an anonymous function as the event handler, it’s best practice to create a named event handler function. Your code will remain organized and reusable this way, even if your code gets complex. Check out the syntax:

```JavaScript 

function eventHandlerFunction() {  
  // this block of code will run when click event happens  
}  
  
eventTarget.addEventListener('click', eventHandlerFunction);
```

The named function `eventHandlerFunction` is passed as the second argument of the `.addEventListener()` method instead of defining an anonymous function within the method! <mark style="background: #ABF7F7A6;">The .on method is introduced below </mark>

---

### Adding Event Handlers

We looked at registering event handlers using the `.addEventListener()` method, but there is also another way!

Event Handlers can also be registered by setting an `.onevent` property on a DOM element (event target). The pattern for registering a specific event is to append an element with `.on` followed by the lowercased event type name. For instance, if we want to register a click event with this pattern, we would write:

```JavaScript 
eventTarget.onclick = eventHandlerFunction;
```

Here, we give the DOM element `eventTarget` the [`.onclick` property](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick) and set its value as the event handler function `eventHandlerFunction`.

It’s important to know that this `.onevent` property and `.addEventListener()` will both register event listeners. With `.onevent`, it allows for one event handler function to be attached to the event target. <mark style="background: #ABF7F7A6;">However, with the `.addEventListener()` method , we can add multiple event handler functions. </mark>In the later exercises, we’ll be using the `.addEventListener()` syntax, but we wanted to also introduce the `.onevent` syntax because both are widely used.

---

### Removing Event Handlers

The `.removeEventListener()` method is used to reverse the `.addEventListener()` method. This method stops the event target from “listening” for an event to fire when it no longer needs to. `.removeEventListener()` also takes two arguments:

1. The event type as a string
2. The event handler function

Check out the syntax of a `.removeEventListener()` method with a click event:

```JavaScript 
eventTarget.removeEventListener('click', eventHandlerFunction);
```

Because there can be multiple event handler functions associated with a particular event, `.removeEventListener()` needs both the exact event type name and the name of the event handler you want to remove. If `.addEventListener()` was provided an anonymous function, then that event listener cannot be removed.

---
### Event Object Properties

JavaScript stores events as [`Event` objects](https://developer.mozilla.org/en-US/docs/Web/API/Event) with their related data and functionalities as properties and methods. When an event is triggered, the event object can be passed as an argument to the event handler function.

```JavaScript
function eventHandlerFunction(event){  
   console.log(event.timeStamp);  
}  
  
eventTarget.addEventListener('click', eventHandlerFunction);
```

In the example above, when the `'click'` event is triggered on the `eventTarget`, the `eventHandlerFunction` receives `event`, the Event object, which has information related to the `'click'` event. Then, we log the time it took for the event to be triggered since the document was loaded by accessing the `.timeStamp` property of the `event` object.

There are pre-determined properties associated with event objects. You can call these properties to see information about the event, for example:

- the [`.target` property](https://developer.mozilla.org/en-US/docs/Web/API/Event/target) to reference the element that the event is registered to.
- the [`.type` property](https://developer.mozilla.org/en-US/docs/Web/API/Event/type) to access the name of the event.
- the [`.timeStamp` property](https://developer.mozilla.org/en-US/docs/Web/API/Event/timeStamp) to access the number of milliseconds that passed since the document loaded and the event was triggered.

---
### Event Types

Beyond the `click` event, there are all types of DOM events that can fire in a browser! It’s important to know _most_ events in the DOM take place without being noticed because there are no event handlers connected to them.

It’s also important to know some registered events don’t depend on user interactions to fire. For instance, the `load` event fires after website files completely load in the browser.

Browsers can fire many other events without a user — you can check out a list of events on the [MDN Events Reference](https://developer.mozilla.org/en-US/docs/Web/Events) page.

Many events need user interaction with the DOM to fire. One user interaction event you’ve become familiar with is the `click` event. A `click` event fires when the user presses and releases a mouse button on an element in the DOM.

![[Pasted image 20231128205849.png]]

In the rest of this lesson, you’ll explore more user interaction event types like the mouse and keyboard events. To explore more event types, check out the [MDN Events Reference](https://developer.mozilla.org/en-US/docs/Web/Events).


---
### Mouse Events

When you use a mouse device on a website, _mouse events_ fire. You’ve seen the `click` and `wheel` events, but, there are even more mouse events to explore!

The `mousedown` event is fired when the user presses a mouse button down. This is different from a `click` event because `mousedown` doesn’t need the mouse button to be released to fire.

1. mouseup
2. mousedown
3. mouseover
4. mouseout  

---
### Keyboard Events

Other popular types of events are keyboard events! _keyboard events_ are triggered by user interaction with keyboard keys in the browser.

The `keydown` event is fired while a user presses a key down.
The `keyup` event is fired while a user releases a key.
The `keypress` event is fired when a user presses a key

---
### Review

Congrats, you completed the lesson! Now you’ve learned about JavaScript events and you can leverage these events on the DOM to create interactivity with event handlers.

Let’s review what you’ve learned:

- You can register events to DOM elements using the `addEventListener()` method.
- The `addEventListener()` method takes two arguments: an event type and an event handler function.
- When an event is triggered on the event target, the registered event handler function executes.
- Event handler functions can also be registered as values of `onevent` properties of their event target.
- ==Event object properties like `.target`, `.type`, and `.timeStamp` are used to provide information about the event.==
- The `addEventListener()` method can be used to add multiple event handler functions to a single event.
- The `removeEventListener()` method stops specific event handlers from “listening” for specific events firing.
---
**Propagation and Bubbling:**

- Events in the DOM follow a propagation and bubbling process. When an event occurs on a specific element, it can propagate up or down the DOM hierarchy. You can control this behavior using the `stopPropagation` method.
```JavaScript 
// Example: Stop event propagation
var parentElement = document.getElementById('parentElement');

parentElement.addEventListener('click', function() {
  console.log('Parent element clicked!');
});

var childElement = document.getElementById('childElement');

childElement.addEventListener('click', function(event) {
  console.log('Child element clicked!');
  event.stopPropagation(); // Stop the event from propagating to the parent
});

```
---
Quiz 
Wrongs
![[Pasted image 20231128215223.png]]
Umfamiliars:
![[Pasted image 20231128215410.png]]
![[Pasted image 20231128215456.png]]
![[Pasted image 20231128220316.png]]