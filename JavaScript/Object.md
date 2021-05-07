One can think of an object as an _associative array_ (a.k.a. _map_, _dictionary_, _hash_, _lookup table_). 
The _keys_ in this array are the names of the object's properties.
 A method is a property that can be called

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_accessors

In the `object.property` syntax, the `property` must be a valid JavaScript [identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier).

In the `object[property_name]` syntax, the `property_name` is just a string or [Symbol](https://developer.mozilla.org/en-US/docs/Glossary/Symbol). So, it can be any string, including `'1foo'`, `'!bar!'`, or even `' '` (a space).

https://dmitripavlutin.com/access-object-properties-javascript/#3-object-destructuring

```javascript
const hero = {
  name: 'Batman'
};

// Object destructuring:
const { name } = hero;name; // => 'Batman'
```

https://dmitripavlutin.com/access-object-properties-javascript/#4-when-the-property-doesnt-exist

```javascript
hero.name;    // => undefined
hero['name']; // => undefined
const { name } = hero;
name;         // => undefined
```