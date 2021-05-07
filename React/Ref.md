https://reactjs.org/docs/refs-and-the-dom.html

https://medium.com/@martin_hotell/react-refs-with-typescript-a32d56c4d315

 ### Creating refs with type
```ts
function createRef<T>(): RefObject<T>

interface RefObject<T> {  
	// immutable  
	readonly current: T | null  
}
```

### Accessing refs

> When a ref is passed to an element in `render`, a reference to the node becomes accessible at the `current`attribute of the ref.
```ts
class MyComponent extends Component {  
  private myRef = React.createRef<HTMLDivElement>()
  focus() {  
    const node = this.myRef.current  
	if (node) { // without if, compile error \[ts\] Object is possibly 'null'.  
						// const node: HTMLDivElement | null
    	node.focus()  
	}
  }  
}


```

What React docs say about `current` value ?

> React will assign the current property with the DOM element when the component **mounts**, and assign it back to null when it **unmounts**. ref updates happen before componentDidMount or componentDidUpdate lifecycle hooks.



## Functional Comp

You may not use the ref attribute on functional components because they don’t have instances
If you want to allow people to take a `ref` to your function component, you can use [`forwardRef`](https://reactjs.org/docs/forwarding-refs.html) (possibly in conjunction with [`useImperativeHandle`](https://reactjs.org/docs/hooks-reference.html#useimperativehandle)),


You can, however, use the ref attribute inside a functional component as long as you refer to a DOM element or a class component:

```js
function CustomTextInput(props) {
  // textInput must be declared here so the ref can refer to it  const textInput = useRef(null);  
  function handleClick() {
    textInput.current.focus();  }

  return (
    <div>
      <input
        type="text"
        ref={textInput} />      <input
        type="button"
        value="Focus the text input"
        onClick={handleClick}
      />
    </div>
  );
}
```


https://github.com/DefinitelyTyped/DefinitelyTyped/issues/35572
```ts
`const componentRef = useRef<HTMLDivElement>(null);`
// this ensures that componentRef = `HTMLDivElement | null` 
// which is what the ref prop is expecting rather than `HTMLDivElement | undefined`.
```