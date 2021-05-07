
### Event Loop
`setTimeout` is an api by browser, so it excutes asynly
the time is not exact but minimum, because it waits for other asyns in the callback cueue
time = 0, just defers cb to waiting area, then enter cb cueue immediatly 

**note**
don't put slow function in stack
don't clog cb queue either

### Promise vs callback hell
```js
const my Promise = new Promise((resolve, reject) => {
	if(true) {
		resolve('');
	} else {
		reject('');
	}
});

myPromise.then((message) => console.log(message);)
.catch((message) => console.log(message););
```

Promises are most useful when you have a process that takes an unknown amount of time in your code (i.e. something asynchronous)
 This can be achieved by using the `then` method
 ```js
 myPromise.then((result) => console.log(result));
 ```
 
 https://javascript.info/promise-basics
 The function passed to `new Promise` is called the _executor_. 
 When `new Promise` is created, the executor runs automatically.
 It contains the producing code which should eventually produce the result.
 In terms of the analogy above: the executor is the “singer”.
 
 Its arguments `resolve` and `reject` are callbacks provided by JavaScript itself. Our code is only inside the executor.

When the executor obtains the result, be it soon or late, doesn’t matter, it should call one of these callbacks:

-   `resolve(value)` — if the job finished successfully, with result `value`.
-   `reject(error)` — if an error occurred, `error` is the error object.

The `promise` object returned by the `new Promise` constructor has these internal properties:

-   `state` — initially `"pending"`, then changes to either `"fulfilled"` when `resolve` is called or `"rejected"` when `reject` is called.
-   `result` — initially `undefined`, then changes to `value` when `resolve(value)` called or `error` when `reject(error)` is called.

A Promise object serves as a link between the executor (the “producing code” or “singer”) and the consuming functions (the “fans”), which will receive the result or error. 
Consuming functions can be **registered** (subscribed) using methods `.then`, `.catch` and `.finally`.
```js
new Promise((resolve, reject) \=> { 
/\* do something that takes time, and then call resolve/reject \*/ }) 
// runs when the promise is settled, doesn't matter successfully or not
  .finally(() \=> stop loading indicator)
// so the loading indicator is always stopped before we process the result/error
 .then(result \=> show result, err \=> show error)
```

#### Example
```js
function loadScript(src) {
  return new Promise(function(resolve, reject) {
    let script = document.createElement('script');
    script.src = src;

    script.onload = () => resolve(script);
    script.onerror = () => reject(new Error(`Script load error for ${src}`));

    document.head.append(script);
  });
}

let promise = loadScript("https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js");

promise.then(
  script => alert(`${script.src} is loaded!`),
  error => alert(`Error: ${error.message}`)
);

promise.then(script => alert('Another handler...'));
```

#### Compare
Promises
Promises allow us to do things in the natural order. First, we run `loadScript(script)`, and `.then` we write what to do with the result.
We can call `.then` on a Promise as many times as we want. Each time, we’re adding a new “fan”, a new subscribing function, to the “subscription list”. More about this in the next chapter: [Promises chaining](https://javascript.info/promise-chaining).

Callbacks
We must have a `callback` function at our disposal when calling `loadScript(script, callback)`. In other words, we must know what to do with the result _before_ `loadScript` is called.
There can be only one callback.