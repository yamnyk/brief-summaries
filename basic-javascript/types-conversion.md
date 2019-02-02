## Primitive types conversion
There are 3 primitive types conversions in JS:
 * [String conversion]()
 * [Number conversion]()
 * [Logical conversion]()

### String conversion
`String(value)` - will convert `value` into String type

*Example:*
```javascript
String(123) // will return "123"
String(false) // will return "false"
String(null) // will return "null"
String(undefined) // will return "undefined"
```

`+` - also can convert data type to String, if it has a string in his arguments

*Example:*
```javascript
let b = 'my birth year is ' + 1988; // will be 'my birth year is 1988'
var a = false + ' or true'; // a will be 'false or true'
```

### Number conversion
`Number(value)` - will turn `value` into number, or return NaN

same thing will happen if you plave a `+` beforw the String value

*Example:*
```javascript
let num = Number("15000"); // String becomes a Number and typeof num will return Number
let numPlus = +"15000"; // same thing happen

var isSmth = +true; // 1
const isSmthElse = Number(false); // 0
```

**WARNING**:
If you using `+` way to convert the values, it'll be easier to confuse yourself, cause it is quite hard to recognise tiny little sign in ton of code strings.

#### Special values
```javascript
let f = +null; // 0
let r = Number(undefined) // NaN
```

`null` - don't care about math
```javascript
let i = null >= 0; // true
let j = null > 0; // false, cause null in this case is 0
let k = null == 0; // false, cause null in this case is null
```

`undefines` - is disparately value
```javascript
let g = undefined > 0; // false, cause undefined is NaN in this case 
let h = undefined < 0; // false, cause undefined is NaN in this case 
let k = undefined == 0; // false, cause undefined is undefined with no conversions
```

### Logical conversion
true/false conversion uses in cases like `if(value){}` and in case of using logical operators.

**values become `false`**
 * 0
 * "" (empty string)
 * null
 * undefined
 * NaN
 
`Number` - all numbers become `true`, except 0, NaN -> `false`
String - all becomes `true`, except empty string "" -> `false`
`undefined` and `null` -> `false`
`Object` - all becomes true