```
h1
a:link
.manythings
#onething
*
.box p
.box p:first-child
h1, h2, .intro
```

1.  The browser loads the HTML 
2.  It converts the [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) into a [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) (_Document Object Model_). 
3.  The browser then fetches most of the resources  and linked CSS! JavaScript is handled a bit later on in the process
4.  The browser parses the fetched CSS, and sorts the different rules by their selector types into different "buckets", e.g. element, class, ID, and so on.
5.  The render tree is laid out
6.   Screen painting.
![](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_works/rendering.svg)

https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured