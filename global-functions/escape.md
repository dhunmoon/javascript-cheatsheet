# `escape()`

The `escape()` function computes a new string in which certain characters have been replaced by a hexadecimal escape sequence.

```javascript
escape('abc123');     // "abc123"
escape('äöü');        // "%E4%F6%FC"
escape('ć');          // "%u0107"

// special characters
escape('@*_+-./');    // "@*_+-./"
```