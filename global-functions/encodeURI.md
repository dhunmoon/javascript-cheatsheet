# `encodeURI()`

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