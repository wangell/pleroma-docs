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

## Built-in Types

Integer: u8, u16, u32, u64

Float: f32, f64

Boolean: bool (`#t`/`#f`)

Character: char (```a``)

String: str 

## Conditionals

The match statement handles most conditionals in Pleroma:

```
? 1 == 1
    #t
        io.print("Yes!")
    #f
        io.print("No!")
```

The empty lines can be left off in the case of only one statement:

```
? 1 == 1
    #t io.print("Yes!")
    #f io.print("No!")
```

If no cases are given, an implied true match is inserted:

```
? 1 == 1
    io.print("Yes!")
```

## Control Flow

For statements can be constructed with the pipe operator, similar to math:
```
my-list : [u8] = [1, 2, 3, 4]

x | my-list
    do-something(x)
```

Indices can be extracted from the list by adding an additional variable `i, x | my-list`
