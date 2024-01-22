-- The purpose of a `<form>` is to allow users to input information and send it.
- The `<form>`‘s `action` attribute determines where the form’s information goes.
- The `<form>`‘s `method` attribute determines how the information is sent and processed.
- To add fields for users to input information we use the `<input>` element and set the `type` attribute to a field of our choosing:
    - Setting `type` to `"text"` creates a single row field for text input.
    - Setting `type` to `"password"` creates a single row field that censors text input.
    - Setting `type` to `"number"` creates a single row field for number input.
    - Setting `type` to `"range"` creates a slider to select from a range of numbers.
    - Setting `type` to `"checkbox"` creates a single checkbox that can be paired with other checkboxes.
    - Setting `type` to `"radio"` creates a radio button that can be paired with other radio buttons.
    - Setting `type` to `"text"` and adding the `list` attribute will pair the `<input>` with a `<datalist>` element if the `list` of `<input>` and the `id` of `<datalist>` are the same.
    - Setting `type` to `"submit"` creates a submit button.
- A `<select>` element is populated with `<option>` elements and renders a dropdown list selection.
- A `<datalist>` element is populated with `<option>` elements and works with an `<input>` to search through choices.
- A `<textarea>` element is a text input field that has a customizable area.
- When a `<form>` is submitted, the `name` of the fields that accept input and the `value` of those fields are sent as `name=value` pairs.

Using the `<form>` element in conjunction with the other elements listed above allows us to create sites that take into consideration the wants and needs of our users. Take the opportunity to take what you’ve learned, and apply it!

And 

- Submit Buttons 


use id attribute to link ``<input>`` and ``<label>`` Together 

For example, the following checkbox code: 

```HTML
<form>  
  <p>Choose your pizza toppings:</p>  
  <label for="cheese">Extra cheese</label>  
  <input id="cheese" name="topping" type="checkbox" value="cheese">  
  <br>  
  <label for="pepperoni">Pepperoni</label>  
  <input id="pepperoni" name="topping" type="checkbox" value="pepperoni">  
  <br>  
  <label for="anchovy">Anchovy</label>  
  <input id="anchovy" name="topping" type="checkbox" value="anchovy">  
</form>
```

- each `<input>` has the same value (which is invisible for the form itself) for the `name` attribute. Using the same `name` for each checkbox groups the `<input>`s together. However, each `<input>` has a unique `id` to pair with a `<label>`.


Example for more input types: 
```HTML 
<!DOCTYPE html>

<html lang="en" dir="ltr">

  <head>

    <meta charset="utf-8">

    <link rel="stylesheet" type="text/css" href="style.css">

    <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">

    <title>Textarea element</title>

  </head>

  <body>

    <section id="overlay">

      <img src="https://content.codecademy.com/courses/web-101/unit-6/htmlcss1-img_burger-logo.svg" alt="Davie's Burgers Logo" id="logo">

      <hr>

      <form action="submission.html" method="POST">

        <h1>Create a burger!</h1>

          <section class="protein">

          <label for="patty">What type of protein would you like?</label>

          <input type="text" name="patty" id="patty">

        </section>

        <hr>

        <section class="patties">

          <label for="amount">How many patties would you like?</label>

          <input type="number" name="amount" id="amount">

        </section>

        <hr>

        <section class="cooked">

          <label for="doneness">How do you want your patty cooked</label>

          <br>

          <span>Rare</span>

          <input type="range" name="doneness" id="doneness" value="3" min="1" max="5">

          <span>Well-Done</span>

        </section>

        <hr>

        <section class="toppings">

          <span>What toppings would you like?</span>

          <br>

          <input type="checkbox" name="topping" id="lettuce" value="lettuce">

          <label for="lettuce">Lettuce</label>

          <input type="checkbox" name="topping" id="tomato" value="tomato">

          <label for="tomato">Tomato</label>

          <input type="checkbox" name="topping" id="onion" value="onion">

          <label for="onion">Onion</label>

        </section>

        <hr>

        <section class="cheesy">

          <span>Would you like to add cheese?</span>

          <br>

          <input type="radio" name="cheese" id="yes" value="yes">

          <label for="yes">Yes</label>

          <input type="radio" name="cheese" id="no" value="no">

          <label for="no">No</label>

        </section>

        <hr>

        <section class="bun-type">

          <label for="bun">What type of bun would you like?</label>

          <select name="bun" id="bun">

            <option value="sesame">Sesame</option>

            <option value="potatoe">Potato</option>

            <option value="pretzel">Pretzel</option>

          </select>

        </section>

        <hr>

        <section class="sauce-selection">

          <label for="sauce">What type of sauce would you like?</label>

          <input list="sauces" id="sauce" name="sauce">

          <datalist id="sauces">

            <option value="ketchup"></option>

            <option value="mayo"></option>

            <option value="mustard"></option>

          </datalist>

        </section>

        <hr>

        <section class="extra-info">

          <label for="extra">Anything else you want to add?</label>

          <br>

          <textarea id="extra" name="extra" rows="3" cols="40"></textarea>

        </section>

        <hr>

  

        <section class="submission">

          <!--Add your code below-->

          <input type="submit" value="Submit">

        </section>

      </form>

    </section>

  </body>

</html>
```


### Drop down list 

```HTML 
<form>  
  <label for="lunch">What's for lunch?</label>  
  <select id="lunch" name="lunch">  
    <option value="pizza">Pizza</option>  
    <option value="curry">Curry</option>  
    <option value="salad">Salad</option>  
    <option value="ramen">Ramen</option>  
    <option value="tacos">Tacos</option>  
  </select>  
</form>
```

N.B. 
>It is the value of the `value` attribute that is used in `<form>` submission (notice the difference in the text and `value` capitalization).
>When the `<form>` is submitted, the information from this input field will be sent using the `name` of the `<select>` and the `value` of the chosen `<option>`. For instance, if a user selected Pizza from the dropdown list, the information would be sent as `"lunch=pizza"`.



### Data Lists 

```HTML
<form>  
  <label for="city">Ideal city to visit?</label>  
  <input type="text" list="cities" id="city" name="city">  
  
  <datalist id="cities">  
    <option value="New York City"></option>  
    <option value="Tokyo"></option>  
    <option value="Barcelona"></option>  
    <option value="Mexico City"></option>  
    <option value="Melbourne"></option>  
    <option value="Other"></option>    
  </datalist>  
</form>
```

> Notice, in the code above, we have an `<input>` that has a `list` attribute. The `<input>` is associated to the `<datalist>` via the `<input>`‘s `list` attribute and the `id` of the `<datalist>`.


### Text Area 
 ```HTML 
 <form>  
  <label for="blog">New Blog Post: </label>  
  <br>  
  <textarea id="blog" name="blog" rows="5" cols="30">  
  </textarea>  
</form>
```