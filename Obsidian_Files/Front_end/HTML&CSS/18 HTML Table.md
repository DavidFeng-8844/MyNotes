# Table Cell

Each table cell is defined by a `<td>` and a `</td>` tag.   (which stand for table data)

# Table Rows 
	Each table rows starts with a<tr> and end with a </tr> 
which stand for table rows

#  Table header

		<th>

# Examples

```html
<table>  
  <tr>  
    <th>Person 1</th>  
    <th>Person 2</th>  
    <th>Person 3</th>  
  </tr>  
  <tr>  
    <td>Emil</td>  
    <td>Tobias</td>  
    <td>Linus</td>  
  </tr>  
  <tr>  
    <td>16</td>  
    <td>14</td>  
    <td>10</td>  
  </tr>  
</table>
```
> TO use a vertical one, define the first cell of every row as table head

```html
<table>  
  <tr>  
    <th>Firstname</th>  
    <td>Jill</td>  
    <td>Eve</td>  
  </tr>  
  <tr>  
    <th>Lastname</th>  
    <td>Smith</td>  
    <td>Jackson</td>  
  </tr>  
  <tr>  
    <th>Age</th>  
    <td>94</td>  
    <td>50</td>  
  </tr>  
</table>
```
# Table Caption 

```html
<table>  
  <caption style="text-align:right">My savings</caption>  
  <tr>  
    <th>Month</th>  
    <th>Savings</th>  
  </tr>  
  <tr>  
    <td>January</td>  
    <td>$100</td>  
  </tr>  
</table>  
<br>
```

# Col Group 
```html
<table>  
  <colgroup>  
    <col span="2" style="background-color:red">  
    <col style="background-color:yellow">  
  </colgroup>  
  <tr>  
    <th>ISBN</th>  
    <th>Title</th>  
    <th>Price</th>  
  </tr>  
  <tr>  
    <td>3476896</td>  
    <td>My first HTML</td>  
    <td>$53</td>  
  </tr>  
</table>
```

![[Pasted image 20230926112131.png|400]]

# thead tbody tfoot 

Group different part together in a table

```html
<table>  
  <thead>  
    <tr>  
      <th>Month</th>  
      <th>Savings</th>  
    </tr>  
  </thead>  
  <tbody>  
    <tr>  
      <td>January</td>  
      <td>$100</td>  
    </tr>  
    <tr>  
      <td>February</td>  
      <td>$80</td>  
    </tr>  
  </tbody>  
  <tfoot>  
    <tr>  
      <td>Sum</td>  
      <td>$180</td>  
    </tr>  
  </tfoot>  
</table>
```

# Table Boarders

To add a border, use the CSS `border` property on `table`, `th`, and `td` elements:
```css 
table, th, td{
border: 1-x solid black;
border-collapse: collapse;
}
```


>Use border-collapse to avoid double borders

# Style the tables

```css
table, th, td {  border: 1px solid white;  
  border-collapse: collapse;}  
th, td {  background-color: #96D4D4;}
```

Round Table Borders

```css
table, th, td {  border: 1px solid black;  
  border-radius: 10px;}
```

>Using border-style to modify the border

![[Pasted image 20230926113319.png|200]]

```css
th, td {  border-style: dotted;}
```

## HTML Table Width 


>Use the style attribute to modify the width of a table 

```html
<table style="width:100%">  
  <tr>  
    <th>Lastname</th>  
    <th>Age</th>  
  </tr>
```

>To set the size of a specific column, add the `style` attribute on a `<th>` or `<td>` element:

```html
 <th style="width:70%">Firstname</th> 
```

>To set the height of a specific row, add the `style` attribute on a table row element:

```html
  <tr style="height:200px">  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>50</td>  
  </tr>
```

# Use the Colspan the span a header over several other cols

```html
 <tr>  
    <th colspan="2">Name</th>  
    <th>Age</th>  
  </tr>
```

# Cell padding and Spacing 

>	Cell padding is the space between the cell edges and the cell content 

```css
th, td {  padding-top: 10px;  
  padding-bottom: 20px;  
  padding-left: 30px;  
  padding-right: 40px;}
  ```

>Cell spacing: 

Cell spacing is the space between each cell.

By default the space is set to 2 pixels.

To change the space between table cells, use the CSS `border-spacing` property on the `table` element:

```css
table{
border-spacing: 30px;
}
```


# Table row and Col span

```html
<th colspan="2">Name</th>
```

```html
 <th rowspan="2">Phone</th>
```


# Table effects(Styling)

## Zebra Stripes

### rows

```css
tr:nth-child(even) {  background-color: #D6EEEE;}
```

### Cols

```css
td:nth-child(even), th:nth-child(even) {  background-color: #D6EEEE;}
```


### Combine
```css
tr:nth-child(even) {  background-color: rgba(150, 212, 212, 0.4);}  
  
th:nth-child(even),td:nth-child(even) {  background-color: rgba(150, 212, 212, 0.4);}
```



## Horizontal Dividers

```css
tr {  border-bottom: 1px solid #ddd;}
```

## Hover table

```css
tr:hover {background-color: #D6EEEE;}
```

## Col Groups 

>Style the first few columns together


There is only a very limited selection of CSS properties that are allowed to be used in the colgroup:

>width
>visibility
>background
>border


If you want to style columns in the middle of a table, insert a "empty" `<col>` element (with no styles) for the columns before:

```html
<table>  
  <colgroup>  
    <col span="3">  
    <col span="2" style="background-color: pink">  
  </colgroup>  
  <tr>  
    <th>MON</th>  
    <th>TUE</th>  
    <th>WED</th>  
    <th>THU</th>
```

>Use this property to hide some columns:

``` html
<table>  
  <colgroup>  
    <col span="2">  
    <col span="3" style="visibility: collapse">  
  </colgroup>  
  <tr>  
    <th>MON</th>  
    <th>TUE</th>  
    <th>WED</th>  
    <th>THU</th>
```