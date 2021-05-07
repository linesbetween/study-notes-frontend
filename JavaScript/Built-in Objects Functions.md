#### **`parseFloat()`**
- parses a string 
- returns a floating point number.
	- Or [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) when the first non-whitespace character cannot be converted to a number.
	-   If other than a plus sign (`+`), minus sign (`-` U+002D HYPHEN-MINUS), numeral (`0`–`9`), decimal point (`.`), or exponent (`e` or `E`), it returns the value up to that character.
	-   A _second_ decimal point also stops parsing 
	-   Leading and trailing spaces in the argument are ignored.

-   can also parse and return [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity).
-   converts [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) syntax to [`Numbers`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number), losing precision. This happens because the trailing `n` character is discarded
-   removes leading and trailing 0s

#### **`parseInt()`**
```
parseInt(string [, radix])
```

- `radix` Optional
	- integer between `2` and `36`
	- coerced to a `Number`

- return:
	- integer
	-  `NaN` when
		-   the `radix` is smaller than `2` or bigger than `36`, or
		-   the first non-whitespace character cannot be converted to a number.