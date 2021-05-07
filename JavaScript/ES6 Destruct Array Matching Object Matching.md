```js
var { op, lhs, rhs } = getASTNode() // short handed
var { op: a, lhs: { op: b }, rhs: c } = getASTNode() //deep
// deep
const LOCAL_FORECAST = {
 yesterday: { low: 61, high: 75 },
 today: { low: 64, high: 77 },
 tomorrow: { low: 68, high: 80 }
};
const { today: { low: lowToday, high: highToday } } = LOCAL_FORECAST;

// default values
var obj = { a: 1 } 
var list = [ 1 ]
var { a, b = 2 } = obj 
var [ x, y = 2 ] = list

// param context matching
function f (\[ name, val \])
{ console.log(name, val); } 
function g ({ name: n, val: v }) 
{ console.log(n, v); } 
function h ({ name, val })
{ console.log(name, val); } 
f(\[ "bar", 42 \]); 
g({ name: "foo", val: 7 });
h({ name: "bar", val: 42 });

// Rest Param
const source = [1,2,3,4,5,6,7,8,9,10];
function removeFirstTwo(list) {
 const [ , , ...arr] = list; 
 return arr;
}
const arr = removeFirstTwo(source);
```