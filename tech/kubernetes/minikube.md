# Minikube

Minikube is a tool for locally creating a kubernetes cluster with a single node using VM software.

```text
minikube start
```

This command starts up the minikube cluster by downloading the necessary dependencies and starting the VM. It automatically configures `kubectl` to use the minikube cluster.

```text
minikube stop
```

Stops the minkube cluster and frees up any resources that it was using.

