# Javascript Built in Objects


## List of built in objects category wise.

### Global functions
* decodeURI()
* decodeURIComponent()
* encodeURI()
* encodeURIComponent()
* escape() [Deprecated]
* eval()
* EvalError()
* FinalizationRegistry()
* isFinite()
* isNaN()
* parseFloat()
* parseInt()
* unescaped() [Deprecated]

### Data structure
* Array
* ArrayBuffer
* BigInt
* BigInt64Array
* GibInt64Array
* Boolean
* Date
* Float32Array
* Float64Array
* Infinity
* Int16Array
* Int32Array
* Int8Array
* Intl
* Map
* NaN
* Number
* Object
* Set
* SharedArrayBuffer
* String
* Symbol
* TypedArray
* Uint16Array
* Uint32Array
* Uint8Array
* Uint8ClampedArray
* Undefined
* WeakMap
* WeakRef
* WeakSet


### Other
* AsyncFunction
* AsyncGenerator
* AsyncGeneratorFunction
* Atomics
* DateView
* Error
* Function
* Generator
* GeneratorFunction
* globalThis
* Math
* Promise
* Proxy
* Reflect
* RegExp
* WebAssembly


### Error types
* IntervalError [Non-standard]
* RangeError
* ReferenceError
* SyntaxError
* TypedError
* URIError


## Global Functions

### 1. decodeURI()
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

### decodeURIComponent()

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


