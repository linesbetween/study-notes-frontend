## center things

### vertical an horizontal
https://www.freecodecamp.org/news/how-to-center-anything-with-css-align-a-div-text-and-more/
```css
```css
.container {
  ...
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically and horizontally */
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -25px 0 0 -25px; /* apply negative top and left margins to truly center the element */
}
```
```