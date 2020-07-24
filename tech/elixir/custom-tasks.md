# Custom Tasks

In order to create custom tasks that can be run with [mix](:/3f275de604cc4300b784e5cec9b07469), you must create a `.ex` file with the following format:

```text
defmodule Mix.Tasks.MyTaskName do
    use Mix.Task

    @shortdoc "This is my short documentation"
    def run(_) do
        ...
    end
end
```

The file can be put anywhere, but typically you should put custom task files into `/lib/mix/tasks`.

The important parts are as follows:

`defmodule Mix.Tasks.MyTaskName` Including `Mix.Tasks` in the module means that mix will include the file when looking for tasks.

`MyTaskName` is the name you will use to run the task. In this case, to run the task you would use the command `mix myTaskName`

`use Mix.Task` This directive provides task functionality to the module.

`@shortdoc "..."` If you include this annotation then your task will be displayed when `mix help` is called, with the text used as a summary of the task. If you do not include the annotation, your task will not be listed but will still be usable.

`def run(args) do ... end` This is the code which is run when the task is called. `args` is the list of arguments passed in from the command line.

