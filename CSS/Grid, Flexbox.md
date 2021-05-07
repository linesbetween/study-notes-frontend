## Grid

```css
header {
  grid-column: 1 / 3;
  grid-row: 1;
}

article {
  grid-column: 2;
  grid-row: 2;
}

aside {
  grid-column: 1;
  grid-row: 2;
}

footer {
  grid-column: 1 / 3;
  grid-row: 3;
}
```


The rules for `grid-template-areas` are as follows:

-   You need to have every cell of the grid filled.
-   To span across two cells, repeat the name.
-   To leave a cell empty, use a `.` (period).
-   Areas must be rectangular — you can’t have an L-shaped area for example.
-   Areas can't be repeated in different locations.

```css
.container {
  display: grid;
  grid-template-areas:
      "header header"
      "sidebar content"
      "footer footer";
  grid-template-columns: 1fr 2fr;
  grid-gap: 20px;
}

header {
  grid-area: header;
}

article {
  grid-area: content;
}

aside {
  grid-area: sidebar;
}

footer {
  grid-area: footer;
}
```

https://css-tricks.com/forums/topic/100-height-of-child-when-height-of-parent-is-not-set/
You could try setting the parents position to relative (position: relative;). Then set the child’s position to absolute. You should then be able to give the child top and bottom values (top: 0; bottom: 0;) making it stretch out the entire height of the parent. However this could cause other issues such as the child’s content overflowing out of the child container.


## Flexbox

https://css-tricks.com/understanding-flex-grow-flex-shrink-and-flex-basis/

```css

.flex-container {
  display: flex; /*equiv to
  flex-item {flex: 0 1 auto; } */
  flex-flow: row wrap;
}

.flex-item {
  text-align: center;
  flex: 1 100%;
  /*
   To make all the elements take up the full space of the parent
   set the child elements to `width: 100%`, 
   or set the `flex-basis` to `100%`, 
   or set `flex-grow` to `1`
  */
  /* flex: none | \[ <'flex-grow'\> <'flex-shrink'\>? || <'flex-basis'\> \]
  flex: 0 1 auto; Default flex value
  flex: \[max\] \[min\] \[ideal size\];
  default size based on content
  if ideal size can't fit, shrink until min.
  if other items size grows, shrink until min 
  ** after fitting all content, for remaining spaces in container **
  flex-grow: 
  	If 0, no expanding, size depends on content
  	If all 1, the remaining space in the container will be distributed equally
	to all children. 
  	If one of 2, the remaining space would take up twice as much space 
	as the others
  flex-shrink:
  	`0`: not to shrink
	 Default `1`, “Take up the same amount of space at all times.” 
  flex-basis: default size before the remaining space is  distributed
  	a length (e.g. 20%, 5rem, etc.) or a keyword. 
	The `auto` keyword means “look at my width or height property
	If set to `0`, the extra space around content isn’t factored in. 
	If set to `auto`, the extra space is distributed based on its `flex-grow`
  */
}

#header {
  background: orange;
  height: 64px;
}

#left {
  background: yellow;
  flex: 1 0 0;
}

#right {
  background: greenyellow;
  flex: 1 0 0;
}

#footer {
  background: pink;
  height: 64px;
}

.grid-container {
  display: grid;
  grid-template-columns: 300px 300px;
  grid-template-rows: 64px auto 64px;
  grid-template-areas:
    "header header"
    "left-bar right-bar"
    "footer footer";
}

#grid-header {
  grid-area: header;
  background: orange;
}
#grid-left {
  grid-area: left-bar;
  background: yellow;
}
#grid-right {
  grid-area: right-bar;
  background: greenyellow;
}
#grid-footer {
  grid-area: footer;
  background: pink;
}

```
