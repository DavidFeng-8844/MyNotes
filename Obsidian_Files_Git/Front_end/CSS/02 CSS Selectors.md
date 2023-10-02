We can divide CSS selectors into five categories:

- Simple selectors (select elements based on name, id, class)
- [Combinator selectors](https://www.w3schools.com/css/css_combinators.asp) (select elements based on a specific relationship between them)
- [Pseudo-class selectors](https://www.w3schools.com/css/css_pseudo_classes.asp) (select elements based on a certain state)
- [Pseudo-elements selectors](https://www.w3schools.com/css/css_pseudo_elements.asp) (select and style a part of an element)
- [Attribute selectors](https://www.w3schools.com/css/css_attribute_selectors.asp) (select elements based on an attribute or attribute value)


---
## Combinator Selectors

There are four different combinators in CSS:
- descendant selector (space)
- child selector (>)
- adjacent sibling selector (+)
- general sibling selector (~)

### descendant selector (Space)
The descendant selector matches all elements that are descendants of a specified element.
```css
div ~ p {  background-color: yellow;}
```

### child selector(>)
The child selector selects all elements that are the children of a specified element.
```css
div > p {  background-color: yellow;}
```

### adjacent sibling selector(+)
The adjacent sibling selector is used to select an element that is directly after another specific element.
```css
div + p {  background-color: yellow;}
```

### general sibling selector
The general sibling selector selects all elements that are next siblings of a specified element.
```css
div + p {  background-color: yellow;}
```

---
## Pseudo-Class Selector

A pseudo-class is used to define a special state of an element.
Syntax:
```css
selector:pseudo-class {  property: value;}
```
### Ex:
> combine with HMTL Class:

```css
a.highlight:hover {  color: #ff0000;}
```

### CSS - The :first-child Pseudo-class

In the following example, the selector matches any < p > element that is the first child of any element:
```css
p:first-child {  color: blue;}
```

In the following example, the selector matches the first < i > element in all < p >  elements:
```css
p i:first-child {  color: blue;}
```

In the following example, the selector matches all < i> elements in < p> elements that are the first child of another element:
```css
p:first-child i {  color: blue;}
```



---
## Pseudo Element

>Syntax:

```css
selector::pseudo-element {  property: value;}
```

### First-line pseudo element 

```css
p::first-line {  color: #ff0000;  
  font-variant: small-caps;}
```

**Note:** The `::first-line` pseudo-element can only be applied to block-level elements.

The following properties apply to the `::first-line` pseudo-element:

- font properties
- color properties
- background properties
- word-spacing
- letter-spacing
- text-decoration
- vertical-align
- text-transform
- line-height
- clear


### ::Before and after Element 
The `::before` pseudo-element can be used to insert some content before the content of an element.

```css
h1::before {  content: url(smiley.gif);}
```

The `::after` pseudo-element can be used to insert some content after the content of an element.

### The ::marker selects the marker of the list item



---
## Attribute Selectors

