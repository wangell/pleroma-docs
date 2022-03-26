# Hylic - Alien Types

One of the key features of Pleroma is the ability to interface with foreign clusters.

This can be achieved using the alien reference type `aln`.

```
~wikipedia

ε HelloWorld
	δ main(env: sys.env) -> u8
        aln wiki : wikipedia.Wikipedia = wikipedia.Wikipedia()

```

This creates a messageable object reference, much like a far reference - except that a proxy object is instantiated in its place.
