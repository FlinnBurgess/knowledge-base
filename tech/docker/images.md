# Images

Images are read-only templates used to create containers. They are often composed of layers of other images. They are stored in a docker registry, such as Docker Hub.

When you provide docker with an image, it will first try to find it locally. If it can't, it will instead search the docker repository for the image and add it to your local images.

To see what images you have locally, you can run

```text
docker images
```

### Official Images

You can find official images in `registries` such as Docker Hub. An official image will have the `official` tag below it when you search on the site. It is a good idea to use these since they tend to have clear documentation and follow best practices. They are also reviewed by a dedicated team at Docker, and are updated quickly with security fixes.

### Layers

Images are often composed of layers of other images. For example if an image relies on some MySQL functionality, it could include the official MySQL image as part of itself. In this case, the MySQL image would be considered a `parent`.

We can see the layers that an image consists of by running the command

```text
docker history {repository}:{tag}
```

When we create a new container, we are essentially adding a new layer that allows us to read/write using the system described in the image, without actually changing the underlying image. This allows multiple containers to share a single image.

### Building Images with Dockerfile

If we want to create a container from a [Dockerfile](:/48b9d554dc7948f193108025eb7afdda), then we run the command

```text
docker build [options] {build-context}
```

the process will look for a Dockerfile inside the build-context directory, but you can also pass a Dockerfile in directly if you want.

The build context is a directory which contains all of the files which the build process has access to. When you call build, all of the files inside the build context are compressed and sent to the docker daemon for use.

The `-t` flag allows us to tag a build, usually to denote a new version of the image.

The build process steps through the instructions in the Dockerfile, first spinning up a container with the base image, then spinning up successive containers on top of that, which apply their changes \(based on the Dockerfile RUN instructions\) and commit them, replacing the base image with the expanded version.

### Manually building images

We can manually implement the automated process described above. First we spin up a container using the desired base image, e.g. Debian, and enter it in interactive mode. Now we can make the changes we want, such as installing some software, such as git. Once this change has been made, we exit the container and run the command

```text
docker commit {container id} {repository}:{tag}
```

which will generate a new image with the corresponding repository and tag.

### Changing the tag

To create a new tag associated with an image, we can run the command

```text
docker tag {image id} {new reponsitory name}:{tag/version}
```

If you run `docker images` after running this command you will notice that the new tag corresponds to the same image which you specified, i.e. it is the same image, just re-tagged.

### Removing images

To delete an image you use the following command:

```text
docker rmi {image}
```

Sometimes you may have to force the deletion by including the `-f` flag.

