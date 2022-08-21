# Getting Started

## Docker Quickstart

This requires the latest docker + docker compose to be installed, first.

```
git clone https://github.com/wangell/pleroma
docker compose run pleroma
```

Once inside the container, run:

```
./pleroma start
```

to run the "Hello, world!" example on a single-node cluster.

You're ready to start your Pleroma journey, continue to [allo instructions](./allo.md).

## Manual Installation

Install the prerequisites: `enet` and `libprotobuf`.  This can be achieved on Ubuntu by running

`sudo apt-get install libenet7 libenet-dev protobuf-compiler libprotobuf-dev`

Next, download by cloning the Git repository here:

```
git clone https://github.com/wangell/pleroma
```

Ensure that your locale is UTF-8.  You can do this by adding the following to your .bashrc:

```
export LANGUAGE=en_US.UTF-8
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
export LC_TYPE=en_US.UTF-8
```

Continue to the [installation instructions](./installation.md).
