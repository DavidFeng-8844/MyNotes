
## HTML Links - Syntax

The HTML `<a>` tag defines a hyperlink. It has the following syntax:
```html 
<a href="url"> link text </a>
```

## Target Attribute

- `_self` - Default. Opens the document in the same window/tab as it was clicked
- `_blank` - Opens the document in a new window or tab
- `_parent` - Opens the document in the parent frame
- `_top` - Opens the document in the full body of the window
```html
<a href="https://www.w3schools.com/" target="_blank">Visit W3Schools!</a>
```

## Image and Email as a Link
>Image:
```html
<a href="default.asp">  
<img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">  
</a>
```
>Email:
```html
<a href="mailto:someone@example.com">Send email</a>
```
>Button:
```html
<button onclick="document.location='default.asp'">HTML Tutorial</button>
```

## URLs and Relative URLs

>HOW:

Use a full URL to link a Web page
```html
<a href="https://www.bing.com">Bing</a>
```

Link to a page located in the html folder on the current web site

```html
<a href="/html/default.asp">HTML tutorial</a>
```


## Chapter Summary

- Use the `<a>` element to define a link
- Use the `href` attribute to define the link address
- Use the `target` attribute to define where to open the linked document
- Use the `<img>` element (inside `<a>`) to use an image as a link
- Use the `mailto:` scheme inside the `href` attribute to create a link that opens the user's email program

## HTML Links - Color
```html
<style>  
a:link {  color: green;  
  background-color: transparent;  
  text-decoration: none;}  
  
a:visited {  color: pink;  
  background-color: transparent;  
  text-decoration: none;}  
  
a:hover {  color: red;  
  background-color: transparent;  
  text-decoration: underline;}  
  
a:active {  color: yellow;  
  background-color: transparent;  
  text-decoration: underline;}  
</style>
```

## HTML Links - Buttons
```html
<style>  
a:link, a:visited {  background-color: #f44336;  
  color: white;  
  padding: 15px 25px;  
  text-align: center;  
  text-decoration: none;  
  display: inline-block;}  
  
a:hover, a:active {  background-color: red;}  
</style>
```


## HTML Links - Create Bookmarks

>First use the Use the id attribute to create a bookmarks 

```html
<h2 id="c4">Chapter 4</h2>
```

 > Then add a link to the bookmark
 
 
```html
<a href="#c4">Jump to Chapter 4</a>
```

## Chapter Summary

- Use the `id` attribute (id="_value_") to define bookmarks in a page
- Use the `href` attribute (href="#_value_") to link to the bookmark