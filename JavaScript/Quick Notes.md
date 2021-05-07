compare number to null

NaN, null, undefined

for (let e of array)

//swap
```
[arr[0], arr[1]] = [arr[1], arr[0]];
```

arr = arr.concat // no side effect, must assign value

list of object 
```js
var list = [
    { date: '12/1/2011', reading: 3, id: 20055 },
    { date: '13/1/2011', reading: 5, id: 20053 },
    { date: '14/1/2011', reading: 6, id: 45652 }
];

alert(list[1].date);
```

array  as a map of freq
```js
freq = [];
addFreq(e) {
	freq[e]? freq[e]++ : freq[e] = 1;
// freq[e] = freq[e]++ || 1;
}
```

object as nap of freq
```js
freq = {};
freq[e] = freq[e] + 1 || 1;
freq.e = freq.e + 1 || 1;
```

A number literal like `37` in JavaScript code is a floating-point value, not an integer.  There is no separate integer type in common everyday use.

**ternary**
condition ? null : null // do nothing

Besides `false`, possible falsy expressions are: `null`, `NaN`, `0`, the empty string (`""`), and `undefined`

no "; " after statement!

**check if object in array exists**
`trainers.filter((trainer) => trainer?.age >= 13);`

**Errow Function**
`const name = () => <return value>`
`var name = function() {body}`
Must be CONST