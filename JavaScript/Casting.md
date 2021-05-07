## Converting to strings

```js
String(10) //"10"
(10).toString() //"10"

String(new Date('2019-01-22'))

String(null) //"null"
String(undefined) //"undefined"
String(NaN) //"NaN"

```

## Converting to numbers
```js
Number("1") //1
Number(" 1 ") //1
Number("") //0

Number(true) //1
Number(false) //0

Number(null) //0
Number(undefined) //NaN
Number(NaN) //NaN

//invalid characters, `NaN`.
```


## Converting to booleans
```js
// Others are true
Boolean(false) //false
Boolean(0) //false
Boolean(NaN) //false
Boolean("") //false
Boolean(null) //false
Boolean(undefined) //false
```