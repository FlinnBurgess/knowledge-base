# Managing Containers

### Run

To launch a container using an image, we run the command

```text
docker run {repository}:{tag} {command} {args}
```

Where `command` is a command you want to run on the resulting container.

The `-i` flag will start the container in interactive mode. The `-t` flag creates a pseudo-terminal that attaches stdin and stdout.

If you don't include the `-t` flag without `-i`, you can still use commands like ls, cd, etc. but the presentation will be much worse than if you include `-t`. It is most common to run `-i` and `-t` together, which can be shortened to `-it`

When you use `docker run`, a completely new instance of the container is spun up. This means that any changes you make in one instance of the container, for example adding new files, will not be visible in the new instance.

### Detached mode

If we execute `docker run` with the `-d` flag, the container will run in detached mode. This allows us to keep using the command line after running the container.

### Listing containers

To list all running containers, we execute the command

```text
docker ps
```

To list all containers **including those that have stopped**, include the `-a` flag.

If we want a container to be removed once it stops running, we can include the `--rm` flag when executing `docker run`.

### Naming

To name a container, we can pass the `--name` flag to the run command. If this flag is not provided, Docker will automatically generate a name for the container.

### Inspecting

When a container is created, it is assigned an ID. If we run the command

```text
docker inspect {container id}
```

we will see a detailed summary of that container's information.

### Logs

We can see the logs from a container by running

```text
docker logs {container ID}
```

### Stop

To stop a container from running, we simply run

```text
docker stop {container id OR container name}
```

### Exec

`docker exec` allows us to run commands on a running container. For example, if we want to launch bash in a particular container, we run the command

```text
docker exec -it {container name/id} bash
```

Remember, the `-it` flag opens the container in interactive mode so that we can continue to work with it.

### Container links

Container links allow containers to see each other, and to transfer information between themselves. Links are uni-directional. That is, you have a source container and a recipient container.

To create a link, we pass the `--link {container name}` flag to a `docker run` command, e.g.

```text
docker run -d -p 5000:5000 --link redis dockerapp:v0.3
```

What the --link flag does is update the hosts file of the container to include the IP address of the container that it is linking to. This allows it to work with the data from that machine.

