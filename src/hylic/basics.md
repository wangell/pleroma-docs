# Hylic - Basics

```
~sys

ε HelloWorld
	δ main(env: sys.env) -> u8
		loc a : u8 := 1 + 1
```

The line
```
~sys
```
imports code from another module.

```
ε HelloWorld
```

This line specifies an entity called HelloWorld.  Everything in Pleroma is an entity, except those things that aren't.
Every entity contains data and functions.  An entity specification is not an entity itself - just a blueprint.

```
δ main(env: sys.env) -> u8
```

Says that there is a function `main`, that takes a variable `env` of type `sys.env` and returns an `int`.
The `δ` specifies the function as one with side-effects.  Alternatively, a `λ` specifies the function as pure.  Pure functions cannot perform side-effects.

```
loc a : u8 := 1 + 1
```
Says to create a variable `a` of type `u8` and set its contents to `1 + 1`.  The type of `a` is a `loc u8`, further explained later in [Messaging, Entities, Vats](./hylic/messaging.md).  By default, all variables are local.  Local variables mean local to the entity.
