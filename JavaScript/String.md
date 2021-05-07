
**string is IMMUTABLE**

### **`indexOf()`**, **`search()`**
**`indexOf()`** method returns the index within the calling [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object of the first occurrence of the specified value, starting the search at `fromIndex`. Returns `-1` if the value is not found.

 **`search()`** search a regular expression in this [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object.

###  **`replace()`**
```
const newStr = str.replace(regexp|substr, newSubstr|function)
```
returns a new string with 
**some or all **matches of a `pattern` replaced by a `replacement`. 
- The `pattern` can be a string 
    - If `pattern` is a string, only the **first** occurrence will be replaced.
    - or a [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) 
- the `replacement` can be a string or a function to be called for each match. 

### **`slice()`**
extracts a section of a string
returns it as a new string, 
without modifying the original string.
```js
str.slice(beginIndex[, endIndex])
```
- beginIndex
	- zero based, inclusive
	- if < 0, str.length + beginIndex
	- if > str.length, return empty
- endIndex
	- zero based, exclusive
	- if omitted, > str.length, slice to the end
	- if < 0, str.length + endIndex
	- if < beginIndex, return empty
- return
	- a new string

### **`split()`**
```js
str.split([separator[, limit]])
```
- `separator`: string or regexp
-`limit`:  the number of substrings to be included in the array
- return: array of strings


## ES6

###Template Literals
String Interpolation
Intuitive expression interpolation for single-line and multi-line strings.

```js
// ECMAScript 6
var customer = { name: "Foo" }; var card = { amount: 7, product: "Bar", unitprice: 42 }; 
var message = `Hello ${customer.name}, want to buy ${card.amount} ${card.product} for a total of ${card.amount * card.unitprice} bucks?`;

// ECMAScript 5
var customer = { name: "Foo" }; var card = { amount: 7, product: "Bar", unitprice: 42 }; 
var message = "Hello " + customer.name + " " + "want to buy " + card.amount + " " + card.product + " for " + "a total of " + (card.amount * card.unitprice) + " bucks?";
```

Custom Interpolation
Flexible expression interpolation for arbitrary methods.
```
// ES6
get\`http://example.com/foo?bar=${bar + baz}&quux=${quux}\`;

// ES5
get(\[ "http://example.com/foo?bar=", "&quux=", "" \],bar + baz, quux);
```