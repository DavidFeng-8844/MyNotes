- Container
- Row 
- Column 
## Key Examples 
### Center an image in the carousel
```HTMl
<div class="carousel-item">
  <div class="row">
    <div class="col text-center my-auto">
      <img class="img-fluid" src="content/gears/images/adizero8.jpg" alt="adidas-adizero-8 " style="height: 45vh;">
    </div>
  </div>
</div>
```
==Using text center for horizontal center and my-auto for vertically center== 
> [Bootstrap 4 Vertical Center. How to vertically align anything | by Carol Skelly | WDstack | Medium](https://medium.com/wdstack/bootstrap-4-vertical-center-1211448a2eff#:~:text=One%20way%20to%20vertically%20center,col%2Dsm%2D12%20column.)


> [Bootstrap center (horizontal align) - Material Design for Bootstrap (mdbootstrap.com)](https://mdbootstrap.com/docs/b4/jquery/utilities/horizontal-align/)
### Intro to the Grid

Bootstrap simplifies the layout of a website using a grid system. For us to fully take advantage of Bootstrap’s grid system, we need to understand how to structure our HTML.

At the heart of it, _containers_ are the basis of Bootstrap’s grid. Inside containers, we nest _rows_ as immediate children. Then, nested inside rows are _columns_. Inside columns, we put our actual content. Take a look below at an example of this nesting pattern. Don’t worry about the syntax of rows and columns just yet, but do take note of how our HTML is organized:

```
<div class="container">  <div class="row">    <div class="col">      <!-- A column inside a row inside a container! -->    </div>  </div></div>
```

We can gain even more control of our layout once we start nesting rows inside columns and setting widths for our columns! But, first, let’s review how to create a layout using Bootstrap.

---

### Bootstrap Containers

Bootstrap uses a grid system based on [CSS Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox) which organizes content in rows or columns. As seen in the previous exercise, Bootstrap also uses rows and columns and in this exercise we’ll learn about the essential Bootstrap container. Using the Bootstrap grid also allows for _responsive design_, in other words, a website’s layout can change based on the user’s screen size. Read more about grid at [Bootstrap’s grid documentation](https://getbootstrap.com/docs/4.1/layout/grid/).

Bootstrap uses classes to apply CSS rulesets — these rulesets dictate the layout and styling of the element. To create a container, necessary for Bootstrap’s grid, we assign a class of `"container"` to a `<div>` like so:

```
<div class="container"></div>
```

The `<div>` from the example above becomes a Bootstrap container which has a width relative to a user’s screen size, becomes horizontally centered, and has a left and right margin.

If we wanted the container to take up the entire width of the screen we can assign a class of `"container-fluid"`:

```
<div class="container-fluid"></div>
```

Knowing how to use documentation is important. We can always check what classes to add using [Bootstrap’s grid documentation](https://getbootstrap.com/docs/4.1/layout/grid/).

**Note:** the Bootstrap site uses CSS notation for classes, which entails having a `.` before a class name like `.example-class-name`.

---
### Rows

Now that we have an understanding of how the layout works in Bootstrap and how to use containers, let’s focus our attention to rows.

As mentioned in the previous exercise, rows are nested within containers. Also, we can add as many rows as we want inside a container. By default, a row will take up the entire width of its parent container. To create a row we assign a [`class`](https://www.codecademy.com/resources/docs/general/data-structures/class) of `"row"` to an element. Take a look at the provided example with a nested row inside a container:

```
<div class="container">  <div class="row">  </div></div>
```

Let’s now add some rows to our web page!

---
### Columns

We’ve covered containers and rows, now we have to go one level deeper and explore Bootstrap’s columns.

Columns are the immediate children of rows and store content. By default, a column will take up the entire width of its parent row. As we add more columns inside a row, the default behavior is for each column’s width to be readjusted to fit in the row — each column will have the same width. At most, a row will accommodate 12 columns. Study the diagram below to see how column sizing works:

![[Pasted image 20231219203733.png]]

Notice the first row in the diagram has 1 column and it takes up the entire width of the row. We could say that this column takes up the width of 12 individual columns. The width of an individual column can be seen in the last row of the diagram.

To create a column, we assign an element with the `class` of `"col"`. Take a look at the provided example with a container that has a nested row which has a nested column:

```
<div class="container">  <div class="row">    <div class="col">    </div>  </div></div> 
```

Let’s learn about this first hand by adding columns in our code!

---
### Setting Column Widths

In the previous exercise, we saw how columns take on a default width based on the size of the row. However, Bootstrap gives us more customization options so that we can make columns of varying widths. Take a look at 4th and 5th row of the diagram for examples of rows containing columns of differing widths:

![[Pasted image 20231219210234.png]]

We can decide the width of a column by appending a hyphen and a number to the `"col"` class like so:

```html
<div class="col-8">  
		<p>This is the width of 8 columns.</p>
</div>
```

In our example, our row still has 4 columns worth of space. If we decide to add an adjacent column, we could also set our desired width like so:

```HTML
<div class="row"> 
	<div class="col-8">   
		<p>This is the width of 8 columns.</p> 
	</div> 
	<div class="col-4">   
		<p>This has the width of 4 columns.</p> 
	</div>
</div>
```

If we didn’t specify a desired width for the second column, it would still resize itself to fill in the remaining space in the row. But, by adding `"-4"`, we make our code more readable and allow other developers to clearly know our intentions.

---
### Setting Column Width with Content

Another option we could use to set the width of a column is the content inside the column.

If we want to use the content to set a column’s width, we append `"auto"` to the `class` of the column, for example:

```HTML
<div class="col-auto"> 
	<p>This content determines the width of the parent column</p></div>
```

In the example above, the width of the column is determined by the text inside the `<p>` element.

---
### Bootstrap Breakpoints

One benefit of using Bootstrap is that it incorporates _responsive design_. With responsive design, the layout of the content changes to accommodate a user’s screen size.

Bootstrap categorizes screen sizes into 5 categories or as _breakpoints_: extra small, small, medium, large, and extra large. Each breakpoint has a range measured in pixels. The range of these breakpoints and accompanying device types are marked in the following table:

|Category|Breakpoint Range|Device Type|
|---|---|---|
|Extra small|< `576 px`|portrait smartphones|
|Small|≥ `576 px`|landscape smartphones|
|Medium|≥ `768 px`|tablets|
|Large|≥ `992 px`|desktops|
|Extra Large|≥ `1200 px`|large desktop|

  

By using these breakpoints in combination with Bootstrap’s grid, we can customize the layout of our content for different screens.

---
### Breakpoint Naming Convention

Using Bootstrap, we can freely change the layout of our content using grid. We can even customize how our content on the grid changes based on breakpoints (extra small, small, medium, large, extra large). To incorporate these breakpoints into our code, we have to follow Bootstrap’s class naming convention.

The naming convention follows a pattern of `"col-{breakpoint}-{width}"`. Let’s break this pattern down:

- As seen before `"col"` refers to a column.
- `{breakpoint}` can be `sm`, `md`, `lg`, or `xl`. Notice that there is no extra small or `xs` breakpoint. If we omit `{breakpoint}`, it is by default for extra small screens.
- `{width}` can be set from `1` to `12` and assigns a width to the column.
- When we set a `{breakpoint}-{width}`, it means that we want our column to have that set width for screens that fit in the specified breakpoint range and other larger screens.

For instance:

```
<div class="col-sm-8"> </div>
```

The column in the example will be as wide as 8 individual columns on small screen sizes and also any larger screens (medium, large, and extra large). In the next exercise, we’ll go over how to customize our layout for every breakpoint. For now, let’s get comfortable with Bootstrap’s naming convention. To get even more information check out [Bootstrap’s grid options documentation](https://getbootstrap.com/docs/4.2/layout/grid/#grid-options).

---
### Bootstrap 4 Grid Review

Great job navigating through Bootstrap’s grid!

Let’s review some key concepts:

- When in doubt, check [Bootstrap’s documentation](https://getbootstrap.com/docs/4.1/getting-started/introduction/).
- There are a few required links to use Bootstrap (the CSS file and two `<meta>` tags)
- Bootstrap 4 has a grid system implemented using flexbox
- The grid system is made of containers, rows, and columns that work together to make a web page’s layout.
- Containers are needed to implement the grid.
- Containers hold rows which hold columns.
- Bootstrap’s grid follows a 12 column system.
- Bootstrap uses responsive design and is built around breakpoints related to device screen sizes.
- To manually set the width of a column we have to follow Bootstrap’s naming convention.
- We can add multiple classes to a column to determine how wide a column should be on specific breakpoints.
![[Pasted image 20231219214459.png]]