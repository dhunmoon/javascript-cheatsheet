# `FinalizationRegistry()`

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