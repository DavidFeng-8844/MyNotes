
## Under a parent block
You can also use CSS Grid to align containers to the left and right:
>HTML


```html
<div class="parent">
  <div class="left-container">Left Content</div>
  <div class="right-container">Right Content</div>
</div>

```
```css
.parent {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.left-container {
  /* Your styles for the left container */
}

.right-container {
  /* Your styles for the right container */
}

```