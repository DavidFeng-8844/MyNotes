
# Unordered List

An unordered list starts with the `<ul>` tag. Each list item starts with the `<li>` tag.

>Style:

The CSS `list-style-type` property is used to define the style of the list item marker. It can have one of the following values:

|Value|Description|
|---|---|
|disc|Sets the list item marker to a bullet (default)|
|circle|Sets the list item marker to a circle|
|square|Sets the list item marker to a square|
|none|The list items will not be marked|



```html
<ul style="list-style-type:dics;">  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ul>
```
# An ordered list 
starts with the < ol > tag instead
```html 
<ol>
 <li> 1</li>
 <li> 2</li>
 </ol>
```
>style:
>-the type Attribute

|Type|Description|
|---|---|
|type="1"|The list items will be numbered with numbers (default)|
|type="A"|The list items will be numbered with uppercase letters|
|type="a"|The list items will be numbered with lowercase letters|
|type="I"|The list items will be numbered with uppercase roman numbers|
|type="i"|The list items will be numbered with lowercase roman numbers|


### Example:

```html
<ol type="1">
```


## Ordered list using CSS to describe

```html
<!DOCTYPE html>
<html>
<head>
<style>
ol {
    list-style-type: decimal;
    counter-reset: item 43;
}

li {
    display: list-item;
}

li::before {
    content: counter(item) ". ";
    counter-increment: item;
}
</style>
</head>
<body>
<ol>
    <li>a</li>
    <li>b</li>
    <li>c</li>
</ol>
</body>
</html>

```


# Description Lists

the < dl > tags define the description list and the dt tag define the term and the dd tag define each term 

```html
<dl>  
  <dt>Coffee</dt>  
  <dd>- black hot drink</dd>  
  <dt>Milk</dt>  
  <dd>- white cold drink</dd>  
</dl>
``` 


# Horizontal list

```html
	li {  float: left;}
```


