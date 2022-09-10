[⬅ All Global functions](https://github.com/dhunmoon/javascript-cheatsheet/tree/main/global-functions)
<hr>
# `decodeURIComponent()`

`decodeURIComponent()` treats the entire value passed inside as a thing which needed to be decode.

Look the example below to understand better.
```javascript
decodeURI('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https%3A%2F%2Fmozilla.org%2F%3Fx%3Dшеллы'
decodeURIComponent('https%3A%2F%2Fmozilla.org%2F%3Fx%3D%D1%88%D0%B5%D0%BB%D0%BB%D1%8B')
//'https://mozilla.org/?x=шеллы'
```
## Parameters

`encodedURIComponent` : `string` - encoded string which could be url or not

## Returns

`decodedURIComponent` : `string` - decoded string.

<hr>
[⬅ All Global functions](https://github.com/dhunmoon/javascript-cheatsheet/tree/main/global-functions)