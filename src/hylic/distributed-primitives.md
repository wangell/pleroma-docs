# Hylic - Distributed Primitives

## ARC

Entities outside of ones own vat behave similarly to heap-allocated memory - entities must be manually destroyed.  For that reason, a distributed automatic reference count object can be used to handle destruction of entities (a vat will automatically be destroyed when no more entities remain).

```
~dis

...

dis.Arc.create($myObj)
```

## Transactional / Checkpoint

## CRDTs

## Key-value Store

## Consistent Hashing
