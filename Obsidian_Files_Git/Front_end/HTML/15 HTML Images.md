## HTML Images Syntax

The HTML `<img>` tag is used to embed an image in a web page.

Images are not technically inserted into a web page; images are linked to web pages. The `<img>` tag creates a holding space for the referenced image.

The `<img>` tag is empty, it contains attributes only, and does not have a closing tag.

The `<img>` tag has two required attributes:

- src - Specifies the path to the image
- alt - Specifies an alternate text for the image

>Syntax

```html
<img src="url" alt="alternate">
```


>N.B.

	Use the style to prevent edited by <style>
```html
<!DOCTYPE html>
<html>
<head>
</head>
<sytle>
img {
 with:500px;height:500px;
}
</style>
<body>
<img src="ddd.jpg" alt='"hi" style="with:500px;height:500px;">
</body>
</html>
```
## Chapter Summary

- Use the HTML `<img>` element to define an image
- Use the HTML `src` attribute to define the URL of the image
- Use the HTML `alt` attribute to define an alternate text for an image, if it cannot be displayed
- Use the HTML `width` and `height` attributes or the CSS `width` and `height` properties to define the size of the image
- Use the CSS `float` property to let the image float to the left or to the right

# Image Maps

The HTML `<map>` tag defines an image map. An image map is an image with clickable areas. The areas are defined with one or more `<area>` tags.

Try to click on the computer, phone, or the cup of coffee in the image below:

```html
<img src="workplace.jpg" alt="Workplace" usemap="#workmap">  
  
<map name="workmap">  
  <area shape="rect" coords="34,44,270,350" alt="Computer" href="computer.htm">  
  <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm">  
  <area shape="circle" coords="337,300,44" alt="Coffee" href="coffee.htm">  
</map>
```


# Background Images

## Add it to an element 
```html
<p style=" background-image: url('img_girl.jpg');">
```

>Or specify it in the Style

```html
<style>
p{
background-image: url('img.jog');
}
```

## On page 

```html
<style>  
body {  background-image: url('img_girl.jpg');}  
</style>
```

## Format 

* Background repeat 
* Background cover If you want the background image to cover the entire element, you can set the `background-size` property to `cover.`
* Background Sketch If you want the background image to stretch to fit the entire element, you can set the `background-size` property to `100% 100%`:
```html
<style>  
body {  background-image: url('img_girl.jpg');  
  background-repeat: no-repeat;  
  background-attachment: fixed;  
  background-size: 100% 100%;}  
</style>
```



# The Picture Element 
The HTML `<picture>` element gives web developers more flexibility in specifying image resources.

The `<picture>` element contains one or more `<source>` elements, each referring to different images through the `srcset` attribute. This way the browser can choose the image that best fits the current view and/or device.

Each `<source>` element has a `media` attribute that defines when the image is the most suitable.

```html
<picture>  
  <source media="(min-width: 650px)" srcset="img_food.jpg">  
  <source media="(min-width: 465px)" srcset="img_car.jpg">  
  <img src="img_girl.jpg">  
</picture>
```

**Note:** Always specify an `<img>` element as the last child element of the `<picture>` element. The `<img>` element is used by browsers that do not support the `<picture>` element, or if none of the `<source>` tags match.