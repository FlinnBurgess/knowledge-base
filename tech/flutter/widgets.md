# Widgets

In flutter almost everything is a widget, including the entire app. This also includes thing like alignment, padding and layout.

A widget’s main job is to provide a `build()` method that describes how to display the widget in terms of other, lower level widgets.

### `StatelessWidget`

Stateless widgets are immutable, so their properties are final and can't change.

### `StatefulWidget`

A stateful widget contains state which may change over the lifetime of the widget. A `StatefulWidget` instance must contain an instace of a `State` class.

A `StatefulWidget` should define a method `createState()` which instantiates the relevant state class \(see below\).

### `State`

If you have a stateful widget class called `ExampleClass`, you can create a corresponding state widget like so:

```dart
class ExampleStateClass extends State<ExampleClass> {
    build()

    ...
}
```

