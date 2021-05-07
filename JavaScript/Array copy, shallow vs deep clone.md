https://www.freecodecamp.org/news/how-to-clone-an-array-in-javascript-1d3183468f6a/

### 1\. Spread Operator (Shallow copy)
```js
numbers = [1, 2, 3];
numbersCopy = [...numbers];
```

### 4\. Array.map (Shallow copy)
```js
numbers = [1, 2, 3];
double = (x) => x * 2;
```

`(x) => x` is called [_identity_](https://en.wikipedia.org/wiki/Identity_function). It returns whatever parameter it’s been given.

### 5\. Array.filter (Shallow copy)
### 6\. Array.reduce (Shallow copy)
### 7\. Array.slice (Shallow copy)
### 9\. Array.concat (Shallow copy)
### 10\. Array.from (Shallow copy)

### 8\. JSON.parse and JSON.stringify (Deep copy)
**Note: This one** **safely copies deeply nested objects/arrays**!

```js
nestedNumbers = [[1], [2]];
numbersCopy = JSON.parse(JSON.stringify(nestedNumbers));

numbersCopy[0].push(300);
console.log(nestedNumbers, numbersCopy);

// [[1], [2]]
// [[1, 300], [2]]
// These two arrays are completely separate!
```
