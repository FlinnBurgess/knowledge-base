# Concepts

## Why Pony?

Pony sets out to guarantee that your programs will not have any issues when running, particularly when it comes to concurrency.

## Null safety

Nothing can be null in Pony. If an operation could potentially return a null value, then you must explicitly decide what to do in that situation. You do that by using `try ... else ...` statements.

## The two rules of safe concurrency

#### Many-readers rule

This rule states that if an actor is reading from a reference, then any other actor can also be reading from that reference. However, an actor must wait for all reading actors to finish before it can write to the shared data.

#### Single-writer rule

This rule states that if an actor is writing to a reference, then no other actor can read or write to that reference until the writing actor is finished.

#### How does Pony use these rules?

These two rules are central to how Pony tracks reference capabilities. By using refcaps, you are telling pony how pieces of data can be accessed, and so allow Pony to know when either of the two rules are being violated.

