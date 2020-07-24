# Redis

Redis is an in-memory data structure store. Is is often used as a database, cache and message broker. It has built-in replication and different levels of on-disk persistence. It is widely used across many high-profile services such as twitter timeline and facebook news feed.

Using redis allows you to store and reference data across multiple docker containers. That way you can have multiple services running from different containers but working on the same data.

To do this, we can have a Redis container which acts as a source container in container links. If multiple recipient containers use this redis container as their source, then they effectively share the data.

