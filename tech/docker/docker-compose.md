# Docker Compose

Docker compose allows us to set up multi-container Docker applications with ease.

The more containers an app requires, the more difficult and time-consuming it is to launch each container manually. Docker compose allows us to define all of the containers which need spinning up in a single yaml file: `docker-compose.yml`.

To spin up the containers using this file, we use the command

```text
docker-compose up -d
```

the `-d` flag runs compose in the background.

#### Version

There are 2 versions of docker-compose files: a legacy version 1 which does not have all the features, and the up to date version 2. To specify we are using version 2, we include the line

```text
version: '2'
```

at the beginning of `docker-compose.yml`

Version 2 allows Docker Networking. This makes all services defined in the file to be discoverable to each other by name. This means that we do not need to create container links between them.

#### Services

Under services we define all of the services \(containers\) we want as part of our Docker app. Each service can be described as such

```yaml
services:
    {service name}:
        build: {directory}
        ports: 
            - "{host port}:{container port}"
        volumes:
            - {host directory}:{container directory}
    {service name}:
        image: {image tag}
        .....
```

Every service needs either the `build` or `image` argument.

`build` describes the directory to be used in building the service's image. For example, if `docker-compose.yml` is in the same directory as the Dockerfile for the service being described, we could just pass `.` as the argument.

`image` takes an image name/tag as an argument, and either uses the local copy or downloads the appropriate image if there is none.

`ports` is synonymous with the `-p` flag used when running a container. It exposes the ports passed as an argument externally.

A volume is a directory inside the container which is designated to persist the containers data irrespective of the container's lifecycle. Volumes allow us to make changes on the host machine and see those changes immediately reflected in the container. It also means that we no longer need a `COPY` instruction in our [Dockerfile](:/48b9d554dc7948f193108025eb7afdda).

### Forcing docker compose to rebuild the images

If we make changes to the files used for building an image, then run `docker-compose up -d`, the changes will not be reflected in the container. This is because docker compose will only build a new image if one does not already exist with the name specified in `docker-compose.yml`. To force docker compose to rebuild the images, we must run the command

```text
docker-compose build
```

This causes docker compose to rebuild all of the images described. The next time we run `docker-compose up`, we will see the changes reflected in the container since docker-compose relaunches the container using the new, updated image.

### Listing the containers

We can use the command

```text
docker-compose ps
```

to list all of the containers currently being run by docker compose.

### Showing logs

```text
docker-compose logs -f
```

Shows the logs for all containers being run by docker compose. The `-f` flag allows us to follow the logs, which allows them to update in real-time.

```text
docker-compose logs {container name}
```

Shows the logs for a specific container.

### Stopping

```text
docker-compose stop
```

Stops all running containers without removing them. To start them again we can use

```text
docker-compose up
```

or

```text
docker-compose start
```

### Removing containers

```text
docker-compose rm
```

Will remove the containers entirely.

