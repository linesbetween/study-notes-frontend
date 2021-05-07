```js
var myArray = new Array(80);
```
This will create an empty array with 80 slots initialized with the value `undefined`.

e.g. arr.push(X) modifies the original array
\[...arr, X\], makes a copy of the array and adds X to it

#### **`map()`**
**creates a new array**
```js
let newArray = arr.map(callback(currentValue[, index[, array]]) {
  // return element for newArray, after executing something
}[, thisArg]);
```

ou shouldn't be using `map` if:
-   you're not using the array it returns; and/or
-   you're not returning a value from the callback.

#### **`filter()`**
**creates a new array** 
```js
let newArray = arr.filter(callback(currentValue[, index[, array]]) {
  // return element for newArray, if true
}[, thisArg]);
```

#### **`splice()`**
**changes** the contents of an array by removing or replacing existing elements and/or adding new elements
```js
let arrDeletedItems = arr.splice(start[, deleteCount[, item1[, item2[, ...]]]])
```
- start: 
	- if > array.length, will be array.length, adding to the end
	- if < 0, array.length - n
- deleteCount: 
	- if omitted or > length - start, all element from start will be deleted
	- if <=0, no delete, but need to specify item to replace with
- returns An array containing the **deleted** elements.
