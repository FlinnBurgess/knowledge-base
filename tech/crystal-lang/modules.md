# Modules

Modules are a way of grouping code into a single namespace.

```text
module ModuleName
    def self.functionName()
        ....
    end

    def self.anotherOne()
        ....
    end
end
```

In the example above we have a module containing two functions. We could then call one of the functions using

```text
ModuleName.functionName()
```

