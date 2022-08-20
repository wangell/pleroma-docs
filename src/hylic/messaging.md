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
myProm : @u8 := anObject ! doThing
```

Promises can be resolved using the resolution operator:

```
@ promise-example
    # do something with the returned value, promise-example
    
@ let x : [@] = [more-promises1, more-promises2, more-promises3]
    # Resolve several promises
```

In this case, each promise variable is shadowed by the resolved version.

## Vats

Vats form local object-graphs - they execute parallel to eachother.  Every program starts in its own vat.  All objects created within that vat can be accessed via a regular function call, e.g. `myObject.doThis()`.  The function will then run synchronously.  To access objects outside of one's own vat, messaging must be used, e.g. `myObject ! doThis()` - which executes asynchronously.  Objects within a vat can also be called asynchronously - but calls will not run parallely, only concurrently.  One can think of a vat like a thread.

Use the following syntax to construct an object in a new vat:

```
$anObject(1)
```

Constructing a new vat always returns the type `@ far object-type`, e.g.:

```
myProm : @far anObject := $anObject()

@ myProm
    # The promise is resolved to a far anObject, we can send messages now
    myProm ! doThing
```

Alternatively, messages can be sent directly to the promise before resolution.  The messages will be preloaded in the message queue during vat formation.

```
myProm : @ far anObject := $anObject()

myProm ! doThing
```

## Message Processing

One of the key features of Pleroma is the ability to mix async and synchronous code.  It is important to understand this feature, as it is enabled by default: all code must yield or the vat will never receive messages.

To implement an infinite loop within a vat, one must use self-messaging:

```
ε HelloWorld
	δ loop() -> ()
        do-something()
        ! loop
```
