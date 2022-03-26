# Getting Started - Configuration

Use a text editor to edit pleroma.yaml.

Assign a name and a network device for the cluster.

```
---
name: bruno
netdev: tun0
```

Configure the resources that will be made available to the cluster:

```
resources:
    - keyboard
    - monitor
    - mouse
    - gpu
```

Use tags to configure node-specific values that will be used during constraint satisfaction.

```
tags:
    safe: ~
    stability-rating: 4
```
