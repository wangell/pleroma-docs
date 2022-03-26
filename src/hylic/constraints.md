# Hylic - Entity Constraints

Entities can be configured to be scheduled according to constraints.  If an Entity is imported into a vat, the vat inherits the constraints.  Collisions between constraints must be handled manually.

Constraints consist of a list of either tags or boolean expressions.  A tag preceded by an & operator will call the equivalent function.  A true boolean function/expression means that the object is able to be scheduled on a node.

```
ε HelloWorld
    - keyboard
    - monitors > 2
    & boolean-callback

	δ boolean-callback(node: node.env) -> bool
        ...
        ↵ #t

```
