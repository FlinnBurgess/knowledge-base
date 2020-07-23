# Testing

Testing follows a similar pattern to that in Javascript. A test in Crystal takes the following form:

```text
describe ClassName do
    it "description of what it should do" do
        .... {expected behaviour}
    end
end
```

### Naming test files

Filenames for test files should typically follow the format `{class}_spec.cr`. You can run all of your tests from the root folder of the project by running

```text
crystal spec
```

but files that don't contain `_spec` in the name won't be included.

### `should`

```text
someValue.should expectation
```

`should` allows us to make assertions in a test. The `expectation` part of this is used to check a particular property of `someValue`. Crystal has several expectation methods, for example `eq`:

```text
myNumber.should eq(5)
```

this assertion will be true when `myNumber == 5`

