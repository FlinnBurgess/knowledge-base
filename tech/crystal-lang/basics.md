# Basics

### `puts`

`puts` stands for put string, and outputs the text it is given

### Filetype

The crystal filetype is `.cr`

### `crystal eval`

`eval` executes the code that is passed to it. For example:

```text
crystal eval 'puts "Hello, world!"'
```

will print out the line "Hello, world!"

### `crystal run`

`run` builds and runs a source file, storing the built code in temporary storage

### `crystal build`

`build` builds an executable that can be run without needing to compile every time. If you don't include the `--no-debug` flag, then `build` will also generate a `.dwarf` file that contains debugging information.

### Building for release

By including the `--release` flag with the build command, the compiler optimises the code for execution speed, rather than compilation speed.

### Running tests

To run a test file you use the command

```text
crystal spec path/to/test/file.cr
```

### Symbols

Symbols are essentially strings which are defined only once across the program, similar to constants. Symbols are defined like so:

```text
:symbol
```

or for multi-word symbols:

```text
:"multi word symbol"
```

You can get a string representation of a symbol by calling:

```text
:symbol.to_s
```

