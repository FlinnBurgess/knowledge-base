# Shard

A shard in crystal defines the set of dependencies for your app. It is defined in the `shard.yml` file of your application. Here is an example `shard.yml`:

```text
name: rovers
version: 0.1.0

authors:
  - Flinn Burgess <flinn.burgess@gmail.com>

targets:
  rovers:
    main: src/rovers.cr

crystal: 0.31.1

license: MIT

dependencies:
  kemal:
    github: kemalcr/kemal
  rover:
    github: batate/rover
```

### Installing dependencies

To install the dependencies of your project you can use the command

```text
shards install
```

### Requiring dependencies

Once a dependency exists in your `shard.yml` file, you can include that dependency in any of your source code by simply refering to the key in `shard.yml`, rather than explicitly providing the path.

Using the example above, we could insert the line

```text
require "rover"
```

into our code, and the `rover` dependency will be imported.

