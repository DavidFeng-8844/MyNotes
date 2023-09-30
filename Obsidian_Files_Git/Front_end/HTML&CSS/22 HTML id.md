The id attribute Specify a unique id that point to a specific style declaration in a style sheet 
```html
<!DOCTYPE html>  
<html>  
<head>  
<style>  
#myHeader {  background-color: lightblue;  
  color: black;  
  padding: 40px;  
  text-align: center;}  
</style>  
</head>  
<body>  
  
<h1 id="myHeader">My Header</h1>  
  
</body>  
</html>
```

## Difference Between Class and ID

A class name can be used by multiple HTML elements, while an id name must only be used by one HTML element within the page:


## Id with bookmarks

## Example

First, create a bookmark with the `id` attribute:

```html
<h2 id="C4">Chapter 4</h2>
```

Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page:

### Example

```html
<a href="#C4">Jump to Chapter 4</a>
```

[Try it Yourself »](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_id_bookmark)

Or, add a link to the bookmark ("Jump to Chapter 4"), from another page:

```html
<a href="html_demo.html#C4">Jump to Chapter 4</a>
```
