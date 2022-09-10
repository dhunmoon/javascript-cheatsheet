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

#### Parameters
`encodedURI` : `string` - A complete, encoded Uniform Resource Identifier.

#### Return value
`decodedURI` : `string` - decoded URI

```javascript
console.log(decodeURI('https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B');
// Output : https://mozilla.org/?x=шеллы
```

### decodeURIComponent()

