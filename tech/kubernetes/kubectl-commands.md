# Kubectl Commands

## [Kubectl Commands](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands) \([cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)\)

Remember to begin each of these with `kubectl {command}`. Run `kubectl {command} --help` to see a full list of parameters and use cases.

```text
get {resource type} {? resource name}
```

returns a list of resources, for example:

* deployments
* nodes
* pods

```text
describe {resource} {? resource name}
```

shows detailed information about a resource.

```text
logs
```

Prints the logs from a container in a pod.

```text
exec [-it] {pod name} [-c {container}] {command} [args]
```

Execute a command on a container in a pod. For example, we could run the command `bash` to get a terminal session going in that pod.

`-i` passes stdin to the container `-t` will specify that stdin is a TTY

The container argument is useful for pods which might hold more than one container.

```text
run {deployment-name} --image={container-image} --port={port-no}
```

creates a new deployment with the name `deployment-name` using the app image provided and exposed on the port provided.

This command finds a node that can be used to run the specified app. It also schedules the app to run on that node and configures the cluster to reschedule the app instance on a new node whenever needed.

```text
expose {resource type} {resource name} [options]
```

Creates a new service, using the resource passed. One option to be passed is `--type`, which defines the type of the service and which other nodes can see this service.

```text
delete {resource}
```

Delete resources by filenames, stdin, resources and names, or by resources and label selector.

```text
proxy
```

Creates a connection between the host \(e.g. your local machine\) and the kubernetes cluster. This allows direct access to the cluster's API using the IP address provided when you run the command. For example, running `curl {provided-ip:port}/version` will list the version details of the current cluster.

```text
label {object-type} {object-name} {label}
```

Adds a new label to the object identified by the type and name passed. e.g. `kubectl label pod $POD_NAME app=v1`

```text
port-forward {pod name} {local port}:{remote port}
```

This command sets it up so that requests on the local port are forwarded to the remote port on the specified pod/container.

```text
attach {pod name} -c {container}
```

Attaches to a process that is already running inside an existing container so that you can view it's output.

```text
scale [options] {deployment}
```

This command allows us to change scaling settings for a deployment on the fly. So instead of having to update the `deployment.yaml` file of a deployment and relaunch it, we can simply run this command to update, for example, the number of replicas we want to allow.

