# Registries and Repositories

A registry is where you can store your images. You can host your own, or there are public registries such as Docker Hub.

Inside a registry you store images in repositories. Inside a repository you will find several images with the same name, but different `tags`, which usually denote different versions of the image.

### Pushing to Docker Hub

Dokcer hub provides free storage for pubic docker images. To do this, use

```text
docker login --username={username}
```

to log into docker hub, then use

```text
docker push {repository}:{tag}
```

to select and push the local image to your docker hub.

