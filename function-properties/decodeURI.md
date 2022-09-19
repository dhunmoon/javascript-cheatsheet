[⬅ All Global functions](https://github.com/dhunmoon/javascript-cheatsheet/tree/main/global-functions)
<hr>
# `decodeURI()`
`decodeURI` understands the structure of the URI and only decodes the part of URI which needed to be decoded.

For example in the uri `https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B` the encoded part is just the `%D1%88%D0%B5%D0%BB%D0%BB%D1%8B` so it will only decode that part.

Look the example below to understand better.
```javascript
decodeURI('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https%3A%2F%2Fmozilla.org%2F%3Fx%3Dшеллы'
decodeURIComponent('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https://mozilla.org/?x=шеллы'
```

## Parameters
`encodedURI` : `string` - A complete, encoded Uniform Resource Identifier.

## Return value
`decodedURI` : `string` - decoded URI

```javascript
console.log(decodeURI('https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B');
// Output : https://mozilla.org/?x=шеллы
```
<hr>

[⬅ All Global functions](https://github.com/dhunmoon/javascript-cheatsheet/tree/main/global-functions)