# Hylic - Capabilities

Objects in Pleroma can only be accessed/messaged by reference.  It's possible to make your objects accessible from the kernel and to guard them with ACLs.

Entities are able to access unique or node-unique system objects by adding an inoculation to the entity definition:

```
~pleroma
~io

ε MyEntity {pinst : far pleroma.Pleroma, io-ctx: loc io.Io}

  δ main(env: u8) -> int
    let node-id : @u32 = pinst ! get-node-id()
    @ node-id
        ...
        
    io-ctx.println("Testing, 1.2.3.")
```

During object instantiation, the kernel searches for node-unique and then unique objects (tagged in the preamble) until the type is matched.
