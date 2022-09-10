# `isFinite()`

Structure - `isFinite(any) -> [true/false]`

The global `isFinite()` function determines whether the passed value is a finite number. If needed, the parameter is first converted to a number.

```javascript
console.log(isFinite('string'))// false
console.log(isFinite([1,2,3]))// false
console.log(isFinite({1:2}))// false
console.log(isFinite(Infinity))// false
console.log(isFinite(undefined))// false

console.log(isFinite(1/1))// true
console.log(isFinite(1/0))// true
console.log(isFinite(null))// true
console.log(isFinite(123123))// true
console.log(isFinite('123123'))// true
```

It will only return true if the value passed is a Finite number or expression which evaluates to a finite number.
