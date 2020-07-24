# Basic Test Structure

There are two main layout structures in Enzyme:

### `describe`

Describe is used to group a set of related tests together. For example, you might group a set of tests on the basis that they are all failure cases. It is okay to nest describe function calls, since it is a way of laying out your tests. The function takes a descriptor string as it's first argument, and a lambda function as it's second argument, like so:

```text
describe('descriptive string', () => {
    ...
    ...
    ...
});
```

### `it`

It is used to provide the descriptor and code for a particular test case. For example, one of your test cases might be that a failure happens because of an unexpected error, and another might be caused by bad input data. Both of these could fall under the same `describe` function call, but different `it` calls. `it` has the same structure as `describe`:

```text
it('descriptive string'. () =. {
    ...
    ...
    ...
});
```

