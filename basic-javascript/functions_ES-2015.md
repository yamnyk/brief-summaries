## Default values
```javascript
function user(name='Gogi', secondName='Doe',age='Infinity') {
	alert(`User
	name: ${name},
	secondName: ${secondName},
	age: ${age}
	`)
}

user(); //will show default values of arguments in alert window
user(undefined, null, ); //all arguments will be default values, except secondName witch will stay null. It happens because only undefined grantees default values for arguments. 
```

Default values can be expressions
```javascript
function sayHi(who = getCurrentUser().getLogin().toUpperCase()) {
	alert(`Hello ${who}`);
}

function getCurrentUser() {
  return {
  	name: 'Gogi',
  	secondName: 'Doe',
  	getLogin: function () {
  		return `${this.name[0]}.${secondName}`.toLowerCase();
  	}
  };
}
```

## Srpead operator instead of arguments
To get Array of arguments you can use `...` operator.

**It gotta be at the end of arguments of function**, else you will have an exception.

```javascript
function showNames(first, second, ...others) {
  alert(first + ', ' + second + ', ' + others)
}

showNames('Gogi', 'Goga', 'Not Gogi', 'Not Goga') //no meter how many arguments we will give it will always show all of them to us in alert window
```

```javascript
let numbers = [23,34,42,333,666,0];

Math.max(...numbers); //save as Math.max(23,34,42,333,666,0)
```

## Destructuring in parameters
```javascript
function showUserData({name, secondName, age}) {
	alert(`User
	name: ${name},
	secondName: ${secondName},
	age: ${age}
	`)
}

let user = {
	name: 'Gogi',
	secondName: 'Doe',
	age: Infinity,
};

showUserData(user); 
```

You can use it in complex with default values.

```javascript
function showUserData({name = 'John', secondName = 'Hopper', age = '56'} = {}) {
	alert(`User:
	name: ${name},
	secondName: ${secondName},
	age: ${age}
	`)
}

let user = {
	name: 'Gogi',
};

showUserData(user); //alert message will be: User: name: Gogi, secondName: Hooper, age: 56
```

In this case even if you will give no arguments it'll gonna work and return default values.

## The functions `name` property
Every function have a name property with its actual name in it.

```javascript
function firstFunc() {}
function secondFunc() {}

alert(firstFunc.name + ' ' + secondFunc.name) //allert message will be 'firstFunc secondFunc'
```

Anonymous functions with was assigned into the object property of variable will inherit theirs names.

```javascript
let myFunc = function() {};

let o = {
	funcInObj: function() {},
};

alert(myFunc.name + ' ' + o.funcInObj.name); 
```

## Functions in blocks

If you user strict mode and some Functions Declaration was defined in the block, it means that this functions gonna be vivible only in this block.

```javascript
'use strict';

if (true) {

  sayHi(); //will work

  function sayHi() {
    alert("Привет!");
  }

}
sayHi(); //will throw an exception
```

## Arrow functions

```javascript
function someFunc(arg) {return alert(arg)}
//is same that
let someFunc = arg => alert(arg);
```

If you need several arguments, wrap it up with braces
```javascript
let someFunc = (arg1, arg2) => alert(arg1+arg2);

//or use braces in right part for readability
let returnUser = (userName, userAge) => ({
  name: userName,
  age: userAge
}) //this function will return an object with two properties
```

If you have a huge function body - use curly braces
```javascript
let someFunc = (arg1,arg2) => {
	let w = arg1**2;
	let h = arg2**3;
	return w-h;
};

alert(someFunc(2, 1));
```

