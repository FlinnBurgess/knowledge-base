# Containers

Containers are to Images as Objects are to Classes. That is, a container is an instance of an image.

They're a lightweight and portable encapsulations of an environment in which to run applications.

Containers are created from images, and contain all the binaries and dependencies required to run it's application.

When we create a container, we are essentially adding a thin read/write layer on top of the [image](:/a6b7218d02ae4c49aac1662acedcf364) that we specify. When we delete the container, this layer is also deleted, but the underlying image remains unchanged.

### Volumes

Volumes are directories inside a container which are designated for storing data irrespective of a container's lifecycle. They are commonly used to share data between a container and the host machine.

