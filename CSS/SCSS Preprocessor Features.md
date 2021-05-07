Variable
```scss
$color-green: #91ea42;
```

CSS @import makes another HTTP request to fetch another stylesheet, 
while a Sass @import grabs the content from inside your imported file and includes it within the compiled stylesheet.

@mixins
similar to a simple JavaScript function
```scss
// mixin  
@mixin transform($property: scale3d(2, 1.5, 0.5)) {
	-webkit-transform: $property;
	-ms-transform: $property;
	transform: $property;
}

// include mixin
div {
	@include transform();
}
```

@extend rule lets you attach the properties of a class to another class. It brings inheritance

```scss
.button {
	display: inline-block;
}

.button-green {
	@extend .button;
	color: #ffffff;
}
```

Math
```scss
// variable
$nav-height: 60px;

// navigation positioning
body {
	padding-top: $nav-height + 40px;
}

.one-third {  
	width: (100% / 3);
}
```

Loop
 `@each`, `@for`, and `@while`
 
```scss
$facebook: #3b5998;
$twitter: #4099ff;

$colors: (
	"facebook": $facebook,
	"twitter": $twitter
);

@each $key, $color in $colors {
	.color-#{$key} {
		background-color: $color;
	}
	.text-#{$key} {
		color: $color;
	}
}
```

**Nesting**
```scss
nav {
	ul {
		list-style: none;
	}
	li {
		display: inline-block;
	}
	a {
		display: block;
		:hover {
			text-decoration: underline;
		}
	}
}
```

Pre-built functions
```scss
$color: #91ea42;
div {
	background-color: complement($color);
}
```

Framework, libraries, optimizations