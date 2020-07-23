# Concurrency

Crystal uses what it calls `fibers` to achieve concurrency. Fibers are lightweight `threads`.

### `spawn`

To use a fiber in crystal, you use the `spawn` method, like so:

```text
spawn do
  puts "hello world"
end
```

### Yielding

In order for a thread to execute, the currently running thread must `yield` to it. For example, if we were to run the `spawn` example above, nothing would happen, since the code is already running in a fiber and that fiber has not given up control.

In order to allow a new fiber to execute, the current fiber must `yield`. This can be done in several ways, such as:

```text
Fiber.yield
```

There are other situations in which a fiber yields, such as during a `sleep` call, or a file read.

### Channels

To share data between fibers, you use `channels`:

```text
my_shared_string = Channel(String).new
```

Defining the type that the channel expects to receive is important for type safety.

### Communicating using channels

To communicate with channels, we use the `send` and `receive` methods:

```text
my_shared_string = Channel(String).new

spawn do
  puts "second step"
  my_shared_string.send("last  step!")
  puts "third step"
end

puts "first step"
received_message = my_shared_string.receive()
puts received_message
```

In the example above, we see that the `receive` method causes the current fiber to yield, and so the second and third steps can execute, the message is added to the channel, and finally printed out as the last step.

### Mutexes

We can use a `Mutex` to ensure that parts of a program are only accessed by a single fiber at a time.

```text
mutex = Mutex.new()

def self.my_function
    mutex.synchronize do
      some_action()
    end
end
```

