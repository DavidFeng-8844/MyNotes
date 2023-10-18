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

### general sibling selector (~)
The general sibling selector selects all elements that are next siblings of a specified element.
```css
div ~ p {  background-color: yellow;}
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

> Def: The CSS Attribute Selectors is used to select elements with a specified attribute 

>Syntax
	The following selector specify all target attribute  
```css
a[target] {  background-color: yellow;}
```


## [attribute="value"] Selector

The `[attribute="value"]` selector is used to select elements with a specified attribute and value.

```css
a[target="_blank"] {  background-color: yellow;}
```

## CSS [attribute~="value"] Selector

The `[attribute~="value"]` selector is used to select elements with an attribute value containing a specified word.
```css
[title~="flower"] {  border: 5px solid yellow;} 
```

## CSS [attribute|="value"] Selector

The `[attribute|="value"]` selector is used to select elements with the specified attribute, whose value can be exactly the specified value, or the specified value followed by a hyphen (-).

**Note:** The value has to be a whole word, either alone, like class="top", or followed by a hyphen( - ), like class="top-text".

```css
[class|="top"] {  background: yellow;} 
```

## CSS [attribute^="value"] Selector

The `[attribute^="value"]` selector is used to select elements with the specified attribute, whose value starts with the specified value.

The following example selects all elements with a class attribute value that starts with "top":

**Note:** The value does not have to be a whole word!

```css
[class^="top"] {  background: yellow;}
```

## CSS [attribute$="value"] Selector

The `[attribute$="value"]` selector is used to select elements whose attribute value ends with a specified value.

```css
[class$="test"] {  background: yellow;}
```

## CSS [attribute*="value"] Selector

The `[attribute*="value"]` selector is used to select elements whose attribute value contains a specified value.

```css
[class*="te"] {  background: yellow;}
```

# Summary
## All CSS Attribute Selectors

|Selector|Example|Example description|
|---|---|---|
|[[_attribute_]](https://www.w3schools.com/cssref/sel_attribute.php)|[target]|Selects all elements with a target attribute|
|[[_attribute_=_value_]](https://www.w3schools.com/cssref/sel_attribute_value.php)|[target="_blank"]|Selects all elements with target="_blank"|
|[[_attribute_~=_value_]](https://www.w3schools.com/cssref/sel_attribute_value_contains.php)|[title~="flower"]|Selects all elements with a title attribute that contains a space-separated list of words, one of which is "flower"|
|[[_attribute_\|=_value_]](https://www.w3schools.com/cssref/sel_attribute_value_lang.php)|[lang\|="en"]|Selects all elements with a lang attribute value starting with "en"|
|[[_attribute_^=_value_]](https://www.w3schools.com/cssref/sel_attr_begin.php)|a[href^="https"]|Selects all <a> elements with a href attribute value starting with "https"|
|[[_attribute_$=_value_]](https://www.w3schools.com/cssref/sel_attr_end.php)|a[href$=".pdf"]|Selects all <a> elements with a href attribute value ending with ".pdf"|
|[[_attribute_*=_value_]](https://www.w3schools.com/cssref/sel_attr_contain.php)|a[href*="w3schools"]|Selects all <a> elements with a href attribute value containing the substring "w3schools"|