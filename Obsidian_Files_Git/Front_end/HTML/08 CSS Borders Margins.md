Margins are used to create Space around elements, outside of any defined borders. 

## Margin - Individual Sides

CSS has properties for specifying the margin for each side of an element:

- `margin-top`
- `margin-right`
- `margin-bottom`
- `margin-left`


```css
p {  margin-top: 100px;  
  margin-bottom: 100px;  
  margin-right: 150px;  
  margin-left: 80px;}
```


## Shorten Version

- **margin: 25px 50px 75px 100px;**
    - top margin is 25px
    - right margin is 50px
    - bottom margin is 75px
    - left margin is 100px 

## Inherit Value 

The example allow the left margin of the < p class = "ex1"> Element be inherited from the parent element (< div > )
```css
div {  border: 1px solid red;  
  margin-left: 100px;}  
  
p.ex1 {  margin-left: inherit;}
```

## Margin Collapse

