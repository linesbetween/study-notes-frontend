```js
const a \= \[{ foo: 'bar' }\];

const b \= a;

const c \= a.slice(); // shallow copy
c.push({ baz: 'qux' });
c\[0\].foo \= 'updated!';  // impure change, state is updated!
  

//Array.slice() points to  \[0\]
// a -> array --> { foo: 'bar' }
// 			^			 ^
// 			| 				| \[0\]
// 			b 			c

```