[⬅ All Global functions](https://github.com/dhunmoon/javascript-cheatsheet/tree/main/global-functions)
<hr>
# `eval()`

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

## How __indirect__ call is different

1. is always executed in global scope.
2. don't have access to local variables.
3. will not inherit the strictness ot the surrounding scope.
4. var declared using __direct__ will go to the surrounding scope but with __indirect__ it will go to the global scope.
5. __indirect__ don't have access to contextual expressions.

<hr>

[⬅ All Global functions](https://github.com/dhunmoon/javascript-cheatsheet/tree/main/global-functions)