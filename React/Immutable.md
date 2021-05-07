https://blog.logrocket.com/immutability-in-react-ebe55253a1cc/

```js
// This is bad, push modifies the original array 
items.push(newItem); 
// This is good, concat doesn’t modify the original array 
const newItems \= items.concat(\[newItem\]);
```

But sometimes, parts of the DOM are re-render even when they didn’t change as a side effect of other parts that do.

In this case, you could implement the function [shouldComponentUpdate](https://reactjs.org/docs/react-component.html#shouldcomponentupdate) to check if the properties and/or state really changed and return true to leave React to perform the update:

class MyComponent extends Component { // ... shouldComponentUpdate(nextProps, nextState) { if (this.props.myProp !== nextProps.color) { return true; } return false; } // ... }