# Array cheat sheet


## Constructor
### `Array()` is the constructor of an array it is used to crate an array.

#### Array literal notation

Array can be created using the the format below called literal notatin:
```javascript
  const cars = ['Bajaj','Honda'];
  
  console.log(cars.length); // 2
  console.log(cars[0]); // "Bajaj"
```

#### Array constructor with a single parameter

Here you pass length of array you want to create and it will create an array and fill it with `undefined` vaues.

```javascript
const fruits = new Array(2);

console.log(fruits.length); // 2
console.log(fruits[0]);     // undefined
```

### Array constructor with multipe parameters

If you pass more than one parameters then it will treat those values as array items and will create a array where the 
length will be no of parameters passed.

```javascript
const fruits = new Array('Apple', 'Banana');

console.log(fruits.length); // 2
console.log(fruits[0]);     // "Apple"
```
## Static properties

### `get Array[@@species]` Retursn the `Array` constructor.

The Array[@@species] accessor property returns the constructor used to construct return value from array methods. I dont think as a beginner this is something which you will use very often.

## Static methods

### `Array.from(array, mappingFunction, thisArg)` - Createa a new `Array` instance from an array-likfe object or iterable object. re

First argument which is an `Array` or array like value which is required. Other parameters are optional, but lets still go through it. Second parameter is mappingFunction which is nothing but a `function` which will be called for each item while mapping it. Finally the last parameter is thisArg which is `this` when execting inside mappingFunction. It defindes what will be the value of `this` inside mapping function.

First argument can also be `{length: 5}`. which will create an array where value at each index will be `undefinde`.


```javascript
console.log(Array.from('foo'));
// expected output: Array ["f", "o", "o"]

console.log(Array.from([1, 2, 3], x => x + x));
// expected output: Array [2, 4, 6]
```

Quick example of how `Array.from()` works with a mappingFunction

```javascript
// Using an arrow function as the map function to
// manipulate the elements
Array.from([1, 2, 3], (x) => x + x);
// [2, 4, 6]

// Generate a sequence of numbers
// Since the array is initialized with `undefined` on each position,
// the value of `v` below will be `undefined`
Array.from({length: 5}, (v, i) => i);
// [0, 1, 2, 3, 4]
```
### `Array.isArray()` - This method determines wheather the passed vaue is an `Array` or not. It returns `true` or `false` based on what value is passed.

Example
```javascript
Array.isArray([1,2,3]); // true
Array.isArray({foo: 123}); // false
Array.isArray(undefined); //false
Array.isArray('foobar'); //false
```

### `Array.of()` 

Creates a new `Array` instance from variable number of arguments, regardless of number or type of the arguments.

`Array.of(7)` creates an array with single element 7 but `Array(7)` creates an `Array` of length 7 where each value is `undefined`.

Quick pointer though `Array.of(undefined)` will return `[undefined]`, and `Array.of('string')` will be `['string']`.


## Instance properties

### `Array.length` - Returns the length of the Array.

### `Array.prototype[@@unscopables]`


## Instance methods

### `Array.prototype.at()`

Returns the array item at the given index. If the `paraVal >= Array.length` it will return `undefined`.

### `Array.prototype.concat()`

It joins 2 arrays together.

### `Array.prototype.copyWithin()`

Copies a sequesnce of array within an existing array.

### 




