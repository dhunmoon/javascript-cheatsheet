[⬅ error-objects](https://github.com/dhunmoon/javascript-cheatsheet/blob/main/error-objects)
> 🚧 Improvement on the documentation is needed to pack more information in less space.
<hr>

# Error

Use can use `Error()` constructor to create a `Error` object.

## Static Methods

1. `Error.captureStackTrace()` - _A non-standard V8 function that creates the stack property on an Error instance._
2. `Error.stackTraceLimit` - _A non-standard V8 numerical property that limits how many stack frames to include in an error stacktrace._
3. `Error.prepareStackTrace()` - _A non-standard V8 function that, if provided by usercode, is called by the V8 JavaScript engine for thrown exceptions, allowing the user to provide custom formatting for stacktraces._


## Instance Properties

1. `Error.prototype.message` - _Error message. For user-created Error objects, this is the string provided as the constructor's first argument._

2. `Error.prototype.name` - _Error name. This is determined by the constructor function._
3. `Error.prototype.cause` - _Error cause indicating the reason why the current error is thrown — usually another caught error. For user-created `Error` objects, this is the value provided as the `cause` property of the constructor's second argument._
4. `Error.prototype.fileName` - _A non-standard Mozilla property for the path to the file that raised this error._
5. `Error.prototype.lineNumber` - _A non-standard Mozilla property for the line number in the file that raised this error._
6. `Error.prototype.columnNumber` - _A non-standard Mozilla property for the column number in the line that raised this error._
7. `Error.prototype.stack` - _A non-standard property for a stack trace._


## Instance methods

1. `Error.prototype.toString()` - _Returns a string representing the specified object. Overrides the Object.prototype.toString() method._


## Constructor

`Error()`

```javascript
```

### `Error.prototype.message`

```javascript
const err = new Error("Message of the error");

err.message;//Message of the error
```

### `Error.prototype.name` 

By default this is determined by the `Error` constructor used by the user or system. In case of user defined error it can also be changed.

```javascript
var genErr = new Error("Generic Error");

genErr.name;//Error

var evErr = new EvalError("Eval Error");
evErr.name;//EvalError
```

#### Changing the `name` prop of a `Error`

You can put any `String` as the value of `name`, it doesn't has to be one of the predefined error types.

```javascript
var genErr = new Error('Generic Error');
genErr.name = 'EvalError';
genErr.name;//EvalError
```

All error types are almost the same.


<hr>

[⬅ error-objects](https://github.com/dhunmoon/javascript-cheatsheet/blob/main/error-objects)