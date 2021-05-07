Variables
```sass
$font-stack:    Helvetica, sans-serif
body
  font: 100% $font-stack
```

Nesting
```sass
nav
  ul
    margin: 0
    padding: 0
    list-style: none

  li
    display: inline-block

  a
    display: block
    padding: 6px 12px
    text-decoration: none
```

Partials
partial Sass files that contain little snippets of CSS that you can include in other Sass files
`_partial.scss`

Module
```
// _base.sass
$font-stack:    Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stack
  color: $primary-color

// styles.sass
@use 'base'

.inverse
  background-color: base.$primary-color
  color: white
```

Mixin
 make groups of CSS declarations that you want to reuse
 ```
=transform($property)
  -webkit-transform: $property
  -ms-transform: $property
  transform: $property
.box
  +transform(rotate(30deg))
```

Extend
```
/* This CSS will print because %message-shared is extended. */
%message-shared
  border: 1px solid #ccc
  padding: 10px
  color: #333


// This CSS won't print because %equal-heights is never extended.
%equal-heights
  display: flex
  flex-wrap: wrap

.message
  @extend %message-shared

```

Math Operators
```
.container
  width: 100%


article[role="main"]
  float: left
  width: 600px / 960px * 100%
```