## The href(hypertext reference) Attribute

```html
<a href="https://www.w3schools.com">Visit W3Schools</a> 
```
## The src Attribute

```html
<img src="img_girl.jpg">
```

**1. Absolute URL** - Links to an external image that is hosted on another website. Example: src="https://www.w3schools.com/images/img_girl.jpg".

**Notes:** External images might be under copyright. If you do not get permission to use it, you may be in violation of copyright laws. In addition, you cannot control external images; it can suddenly be removed or changed.

**2. Relative URL** - Links to an image that is hosted within the website. Here, the URL does not include the domain name. If the URL begins without a slash, it will be relative to the current page. Example: src="img_girl.jpg". If the URL begins with a slash, it will be relative to the domain. Example: src="/images/img_girl.jpg".

## The width and height Attributes

The `<img>` tag should also contain the `width` and `height` attributes, which specify the width and height of the image (in pixels):

```html 
		<img src="img_suka.jpg" width="500" height="600">
		
```

## The alt Attribute 

The alt attribute for the tag specifies an alternate, if the original can't display, it would show the alt
```html 
		<img src="img_suka.jpg" width="500" height="600" alt="This is an alt ">
		
```

## The Style Attribute 

The style attribute add style to an element 
```html
<p style="color:red;">This is a red paragraph.</p>
```


## The lang Attribute
```html
<!DOCTYPE html>  
<html lang="en">  
<body>  
...  
</body>  
</html>
```


## Chapter Summary

- All HTML elements can have **attributes**
- The `href` attribute of `<a>` specifies the URL of the page the link goes to
- The `src` attribute of `<img>` specifies the path to the image to be displayed
- The `width` and `height` attributes of `<img>` provide size information for images
- The `alt` attribute of `<img>` provides an alternate text for an image
- The `style` attribute is used to add styles to an element, such as color, font, size, and more
- The `lang` attribute of the `<html>` tag declares the language of the Web page
- The `title` attribute defines some extra information about an element