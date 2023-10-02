
## The <!DOCTYPE> Declaration

The `<!DOCTYPE>` declaration represents the document type, and helps browsers to display web pages correctly.

It must only appear once, at the top of the page (before any HTML tags).

The `<!DOCTYPE>` declaration is not case sensitive.

The `<!DOCTYPE>` declaration for HTML5 is:

<!DOCTYPE html>


## HTML Headings

HTML headings are defined with the `<h1>` to `<h6>` tags.

`<h1>` defines the most important heading. `<h6>` defines the least important heading: 

### Example
```html

<h1>This is heading 1</h1>  
<h2>This is heading 2</h2>  
<h3>This is heading 3</h3>

```


## HTML Paragraphs

HTML paragraphs are defined with the `<p>` tag:

### Example
```html
<p>This is a paragraph.</p>  
<p>This is another paragraph.</p>
```

## HTML Links

HTML links are defined with the `<a>` tag:

### Example
```html
<a href="https://www.w3schools.com">This is a link</a>
```

[Try it Yourself »](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_basic_link)

The link's destination is specified in the `href` attribute. 

Attributes are used to provide additional information about HTML elements.

You will learn more about attributes in a later chapter.

## HTML Images

HTML images are defined with the `<img>` tag.

The source file (`src`), alternative text (`alt`), `width`, and `height` are provided as attributes:

### Example

```html
<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142">
```
##  ==HTML Elements==

The HTML **element** is everything from the start tag to the end tag:
```
<tagname>Content goes here...</tagname>
```



## Nested HTML Elements

HTML elements can be nested (this means that elements can contain other elements).

All HTML documents consist of nested HTML elements.

The following example contains four HTML elements (`<html>`, `<body>`, `<h1>` and `<p>`):

### Example
```html
<!DOCTYPE html>  
<html>  
<body>  
  
<h1>My First Heading</h1>  
<p>My first paragraph.</p>  
  
</body>  
</html>
```


==N.B.>==
## HTML is Not Case Sensitive

HTML tags are not case sensitive: `<P>` means the same as `<p>`.
The HTML standard does not require lowercase tags, but W3C **recommends** lowercase in HTML, and **demands** lowercase for stricter document types like XHTML.