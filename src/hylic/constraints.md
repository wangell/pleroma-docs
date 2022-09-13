# Hylic - Entity Constraints

Entities can be configured to be scheduled according to constraints.  If an Entity is imported into a vat, the vat inherits the constraints.  Collisions between constraints must be handled manually.

Constraints consist of a list of either tags or boolean expressions.  A tag preceded by an & operator will call the equivalent function.  A true boolean function/expression means that the object is able to be scheduled on a node.

```
~sys►resources rsc
~sys►node nd

ε HelloWorld
    - nd.is("unixborn")
    - rsc.has("keyboard")
    - rsc.gt("monitors", 2)
    - boolean-callback boolean-collision
    - nd.each()

	δ boolean-callback(env: nd►Env) -> bool
        ...
        ? rsc.present("keyboard")
            ↵ #t

```

Entity constraints marked with `-` form preambles - that is, they are executed within the kernel before object instantiation.  Preamble expressions don't have access to entity members.  They form an execution plan.

Entity constraints marked with `+` form postambles - which run after instantiation.  Postamble expressions have access to entity members.  Not everything can go according to plan, postambles react to and change previously made execution plans.
