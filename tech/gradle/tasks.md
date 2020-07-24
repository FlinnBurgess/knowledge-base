# Tasks

### Task dependencies

When creating a gradle task, we can specify a dependency between two tasks by including it in the definition of the task:

```text
task taskNameOne(dependsOn: taskNameTwo)
```

If a task depends on another one, the depency will run before the dependent task.

### Dot notation vs defining in task body

There are two ways to define parts of a tasks body. Take for example the doFirst part of a task's body, which gets executed before anything else when the task is run. You can define doFirst in the two following ways:

```text
task taskName {
    doFirst {
        println 'Hello world'
    }
}
```

or

```text
task taskName {
}

taskName.doFirst {
    println 'Hello world'
}
```

