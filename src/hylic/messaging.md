# Hylic - Messaging

Messaging can be performed in many different ways in Hylic and is optionally restrictive.

All objects can be called synchronously, asynchronously, and via a Promise-based interface.

## Synchronous Message Passing

When we call an object synchronously, we wait for the response of the object before continuing.
```
anObject.doThing()
```

## Asynchronous Message Passing

```
anObject ! doThing
```
Passes a message and ignores the result.

## Promises

```
myProm : Promise u8 := anObject <- doThing
```

Promises can be resolved using the following methods: ...
