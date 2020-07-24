# Reference Capabilities

Reference capabilities \(refcaps\) are the means by which Pony ensures that a program is safe to execute concurrently.

Refcaps place restrictions on the actions that can be made with a given reference. If the pony compiler detects usage that violates these restrictions then it won't compile.

### Refcaps available

#### `iso`

Isolation. These references are unsafe for concurrency, so Pony allows no more than one to exist at any given time.

#### `val`

These references are immutable. These references cannot be changed, but they can be read and shared with impunity.

#### `ref`

These references are mutable. They can be read and written, but can’t be shared.

#### `box`

These references might be val or ref objects. As a consequence, they can be read, but not written or shared.

#### `tag`

These references are neither readable nor writable, but sharable. Actors can be shared, and you can send messages to them.

#### `trn`

These references may be converted to a val later.

#### Summary

Where `alias` is the process of creating a second variable that points to the first, and `sent` means that the reference can be sent to another actor.

| refcap | read | write | alias | sent |
| :---: | :---: | :---: | :---: | :---: |
| iso | yes | yes | no | yes |
| trn | yes | yes | r | no |
| ref | yes | yes | r/w | no |
| val | yes | no | r | yes |
| box | yes | no | r/w | no |
| tag | no | no | r/w | yes |

### Assigning refcaps

#### Decorating a variable

Add the refcap just after the type of your variable

```text
let name: String val = "Flinn"
```

#### Specify the refcap of a return value

Add the refcap after the return type of a function

```text
fun my_function(): USize val
```

#### Add to function or behaviour arguments

```text
be ride(person: Cowboy iso)
```

#### Specify the type of a caller. Add the refcap before the name of a function. The caller must for example fold a ref to call the following method:

```text
fun ref restricted_function()
```

