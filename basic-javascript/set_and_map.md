# MAP
Map is `key-value` collection.

#### Key can be any of data types, including Object

```javascript
const map = new Map();
const user = { 
	userName:'Gogi', 
    age: 25
};
/*method set() pushes into map kay and value*/
map.set(
	user, //first argument is the key. 
	'access denied' //second argument can be any of data types as well
	);
map.set(true, 1);
map.set(1, 'gogi');
map.set('1', '123'); //attention key str1 and nmbr1 gonna be different keys with different values, be careful with it
	
map.get(user) //returns value assigned to this key
```

#### Maps comparing keys algorithm
Works same as `===` operator and called `SameValueZero`. The only difference between this two is that the `SameValueZero` means that `NaN === NaN`. So NaN can be a used as the key (don't do this!).

#### Deleting elements methods

* `map.delete(key)` - will delete the `key` and assigned value. After this will return `true` if the `key` was in map, and `false` if was no such key in map.

* `map.clear()` - delete all key and values from map. Complete clean it.

#### Is the `key` exist in this map?

`map.has(key)` - return `true` or `false` depends of was orr wasn't the key in the map

### Iterations

`map.keys()` - return iterable object with all **keys** in it

`map.values()` - return iterable object with all **values** in it

`map.entries()` - return iterable object where every item will be key-value pare. `for of` cycle use this method by default.

```javascript
let shoppingMap = new Map([
  ['bread',   '2'],
  ['apples', '1kg'],
  ['bananas',   '1.5kg']
]);

// cycle with keys
for(let fruit of shoppingMap.keys()) {
  alert(fruit); // bead, apples, bananas
}

// cycle with values
for(let amount of shoppingMap.values()) {
  alert(amount); // 2, 1kg, 1.5kg
}

// cycle with key-value pairs
for(let entry of shoppingMap) { //same that recipeMap.entries()
  alert(entry); // returns 2-value-arrays like [bread, 2] and so on
}
```

`map.forEach()` - works like casual forEach() in Arrays or Objects with callback function as an argument

# SET

