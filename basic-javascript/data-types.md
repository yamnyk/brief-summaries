## Data types in JavaScript

There are 6 data types in JS, first 5 of themare - *PRIMITIVES*:
 * [Number](https://github.com/yamnyk/brief-summaries/blob/master/basic-javascript/data-types.md#number)
 * [String](https://github.com/yamnyk/brief-summaries/blob/master/basic-javascript/data-types.md#string)
 * [boolean](https://github.com/yamnyk/brief-summaries/blob/master/basic-javascript/data-types.md#boolean)
 * [null](https://github.com/yamnyk/brief-summaries/blob/master/basic-javascript/data-types.md#null) - special value
 * [undefined](https://github.com/yamnyk/brief-summaries/blob/master/basic-javascript/data-types.md#undefined) - special value
 
 and
 * [Object](https://github.com/yamnyk/brief-summaries/blob/master/basic-javascript/data-types.md#object)
 
### `Number`
**Single type for all** (integer and fractional) numbers.

```javascript
var number = 123;
let someNumber = 321;
num = 1;
```
There two other types '*incide*' of type Number:

#### **`NaN`** - is a calculation error means "*Not a Number*"

*Example:*
```javascript
let a = 'any possible string' + 1 // a - will be NaN cause this is incorrect mathematical operation
```

#### **`Infinity`** - special number value

*Example:*
```javascript
let b = 123/0 // b - will be an Infinity
```

### `String`
Text data type can be created using `"` or `'` quotes around text.

*Example:*
```javascript
var string = "create string using double quotes";
let str = 'create string using single quotes';
```

### `boolean` - logical data type
Have only two values - `true` or `false`. Uses when you need only Yes\No type of value.

*Example:*
```javascript
var checked = false;
let isValid = true;
```

### `null` - special value
This is the separate type of data means `nothing` or `unknown value`. 

**WARNING** - this is **NOT** a link to the *nonexistent Object* or *null pointer*.

*Example:*
```javascript
let age = null //means that age is unknown
```

### `undefined` - special value
is separate data type also, as `null`. But has a different meaning.

**It means - VALUE NOT ASSIGNED**

`undefined` - is the default value of variable right after declaration

*Example:*
```javascript
var gogi; //value of gogi is undefined
```

### `Object`


### `typeof` operator