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

The Array[@@species] accessor property returns the constructor used to construct return value from array methods.





