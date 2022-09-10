[⬅ built-in-objects](https://github.com/dhunmoon/javascript-cheatsheet/blob/main/built-in-objects.md)
> 🚧 Improvement on the documentation is needed to pack more information in less space.
<hr>

# Global functions

### Encoding decoding URI and URI Components
> Order of items in the list is different from how the appear in the documentation below.
* decodeURI() 
* decodeURIComponent()
* encodeURI()
* encodeURIComponent()

### Helpful in validation
* isFinite()
* isNaN()

### Parsing values
* parseFloat()
* parseInt()

### Evaluate JavaScript code stored as string.
* eval()

### Memory management - Difficult to understand and use
* FinalizationRegistry()

### Escape and unescape characters [Deprecated]
* escape() [Deprecated]
* unescaped() [Deprecated]

## 1. `decodeURI()`
`decodeURI` understands the structure of the URI and only decodes the part of URI which needed to be decoded.

For example in the uri `https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B` the encoded part is just the `%D1%88%D0%B5%D0%BB%D0%BB%D1%8B` so it will only decode that part.

Look the example below to understand better.
```javascript
decodeURI('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https%3A%2F%2Fmozilla.org%2F%3Fx%3Dшеллы'
decodeURIComponent('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https://mozilla.org/?x=шеллы'
```

#### Parameters
`encodedURI` : `string` - A complete, encoded Uniform Resource Identifier.

#### Return value
`decodedURI` : `string` - decoded URI

```javascript
console.log(decodeURI('https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B');
// Output : https://mozilla.org/?x=шеллы
```

## 2. `decodeURIComponent()`

`decodeURIComponent()` treats the entire value passed inside as a thing which needed to be decode.

Look the example below to understand better.
```javascript
decodeURI('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https%3A%2F%2Fmozilla.org%2F%3Fx%3Dшеллы'
decodeURIComponent('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https://mozilla.org/?x=шеллы'
```
#### Parameters

`encodedURIComponent` : `string` - encoded string which could be url or not

#### Returns

`decodedURIComponent` : `string` - decoded string.

## 3. `encodeURI()`

The `encodeURI()` function encodes a URI by replacing each instance of certain characters by one, two, three, or four escape sequences representing the UTF-8 encoding of the character (will only be four escape sequences for characters composed of two "surrogate" characters).

It's a bit different from `encodeURIComponent()` as it takes URI structure into consideration and only encodes part which needed to be encoded.

look at this example below to understand the different.
```javascript
codeURI(`https://mozilla.org/?x=шеллы`);
'https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B'
encodeURIComponent(`https://mozilla.org/?x=шеллы`)
'https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B'
```

#### Parameters
`URI` : `string` - a URI

#### Returns
`encodedURI` : `string` - a encoded URI

## 4. `encodeURIComponent()`

The `encodeURIComponent()` function encodes a URI by replacing each instance of certain characters by one, two, three, or four escape sequences representing the UTF-8 encoding of the character (will only be four escape sequences for characters composed of two "surrogate" characters).

look at this example below to understand the different.
```javascript
codeURI(`https://mozilla.org/?x=шеллы`);
'https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B'
encodeURIComponent(`https://mozilla.org/?x=шеллы`)
'https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B'
```

#### Parameters
`string` : `string` - a string 

#### Returns
`encodedURIComponent` : `string` - string is encoded.


## 5. `escape()`

The `escape()` function computes a new string in which certain characters have been replaced by a hexadecimal escape sequence.

```javascript
escape('abc123');     // "abc123"
escape('äöü');        // "%E4%F6%FC"
escape('ć');          // "%u0107"

// special characters
escape('@*_+-./');    // "@*_+-./"
```

## 6. `eval()`

The `eval()` function evaluates JavaScript code represented as a string and returns its completion value. The source is parsed as a script.

`eval(string) -> undefined`

```javascript
console.log(eval('2 + 2'));
// expected output: 4

console.log(eval(new String('2 + 2')));
// expected output: 2 + 2

console.log(eval('2 + 2') === eval('4'));
// expected output: true

console.log(eval('2 + 2') === eval(new String('2 + 2')));
// expected output: false

```
There are two different mode of eval __direct__ and __indirect__. __direct__ is when `eval()` is called directly and __indirect__ is when `eval()` is called using`?.`, assigning it to a different variable or vai a member access or other expression.

#### How __indirect__ call is different

1. is always executed in global scope.
2. don't have access to local variables.
3. will not inherit the strictness ot the surrounding scope.
4. var declared using __direct__ will go to the surrounding scope but with __indirect__ it will go to the global scope.
5. __indirect__ don't have access to contextual expressions.


## 7. `isFinite()`

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


## 8. `isNaN()`

Structure - `isNaN(any|expression) -> true`

Most of the values when converted to number other than `boolean` if is number then it returns `false` else it will return `true`. See the example below.

```javascript
isNaN(NaN);       // true
isNaN(undefined); // true
isNaN({});        // true

isNaN(true);      // false
isNaN(null);      // false
isNaN(37);        // false

// strings
isNaN('37');      // false: "37" is converted to the number 37 which is not NaN
isNaN('37.37');   // false: "37.37" is converted to the number 37.37 which is not NaN
isNaN("37,5");    // true
isNaN('123ABC');  // true:  parseInt("123ABC") is 123 but Number("123ABC") is NaN
isNaN('');        // false: the empty string is converted to 0 which is not NaN
isNaN(' ');       // false: a string with spaces is converted to 0 which is not NaN

// dates
isNaN(new Date());                // false
isNaN(new Date().toString());     // true

// This is a false positive and the reason why isNaN is not entirely reliable
isNaN('blabla');   // true: "blabla" is converted to a number.
                   // Parsing this as a number fails and returns NaN
```

## 9. `parseFloat()`

The `parseFloat()` function parses an argument (converting it to a string first if needed) and returns a floating point number.

Syntax : `parseFloat(string|any)` returns `Number` or `NaN` based on value passed

If the string can be converted to Number then that Number is returned else it returns `NaN`.

## 10. `parseInt()`

`parseInt()` is similar to `paseFloat()` but instead of returning Floating point number in some cases it will return Number. which means '2.33333' -> 2 will be returned.

## 11. `unescaped()` [Deprecated]

The `unescape()` function computes a new string in which hexadecimal escape sequences are replaced with the character that it represents. The escape sequences might be introduced by a function like escape. Usually, decodeURI or decodeURIComponent are preferred over `unescape`.

```javascript
unescape('abc123');     // "abc123"
unescape('%E4%F6%FC');  // "äöü"
unescape('%u0107');     // "ć"
```

## 12. `FinalizationRegistry()`

A `FinalizationRegistry` object lets you request a callback when an object is garbage-collected.

`FinalizationRegistry` provides a way to request that a cleanup callback get called at some point when an object registered with the registry has been reclaimed (garbage-collected). (Cleanup callbacks are sometimes called finalizers.)

You create the registry passing in the callback:

```javascript
const registry = new FinalizationRegistry((heldValue) => {
  // …
});
```

Then you register any objects you want a cleanup callback for by calling the register method, passing in the object and a held value for it:

```javascript
registry.register(theObject, "some value");
```
The registry does not keep a strong reference to the object, as that would defeat the purpose (if the registry held it strongly, the object would never be reclaimed).

If `theObject` is reclaimed, your cleanup callback may be called at some point with the held value you provided for it (`"some value"` in the above). The held value can be any value you like: a primitive or an object, even undefined. If the held value is an object, the registry keeps a strong reference to it (so it can pass it to your cleanup callback later).

If you might want to unregister an object later, you pass a third value, which is the `unregistration` token you'll use later when calling the registry's unregister function to unregister the object. The registry only keeps a weak reference to the unregister token.

It's common to use the object itself as the unregister token, which is just fine:

```javascript
registry.register(theObject, "some value", theObject);
// …

// some time later, if you don't care about `theObject` anymore unregister it
registry.unregister(theObject);
```
It doesn't have to be the same object, though; it can be a different one:

```javascript
registry.register(theObject, "some value", tokenObject);
// …

// some time later
registry.unregister(tokenObject);
```
<hr>

[⬅ built-in-objects](https://github.com/dhunmoon/javascript-cheatsheet/blob/main/built-in-objects.md)


