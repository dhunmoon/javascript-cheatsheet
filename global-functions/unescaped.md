# `unescaped()` [Deprecated]

The `unescape()` function computes a new string in which hexadecimal escape sequences are replaced with the character that it represents. The escape sequences might be introduced by a function like escape. Usually, decodeURI or decodeURIComponent are preferred over `unescape`.

```javascript
unescape('abc123');     // "abc123"
unescape('%E4%F6%FC');  // "äöü"
unescape('%u0107');     // "ć"
```