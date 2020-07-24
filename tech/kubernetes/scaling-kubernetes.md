# Scaling Kubernetes

### Replicas

Kubernetes allows you to define replicas when you deploy an application - there are a few options:

* Setting replicas configuration in `deployment.yaml` \(recommended\)
* Defining a ReplicaSet
* Bare pods
* Job
* DaemonSet

You can ignore most of these until you come across them in the future, the most useful and important one is setting the configuration in `deployment.yaml`

### Deployment configuration

Take a look at the example configuration in [Deployments](:/80511e6ee89943dab1577d8514f64ed2). The `replicas` parameter defines how many copies of the relevant pod we would like to run. We can run as many replicas as we have resources for.

Creating additional replicas provides redundancy and higher capacity in your application.

### Exposing multiple replicas

When we create multiple replicas of a pod, we should no longer use the `NodePort` type for the service, since this exposes a single port on a single pod.

Instead we should use the `LoadBalancer` type, which will split the requests among the different replicas, like so:

```text
kubectl expose deployment {deployment name} --type=LoadBalancer --port={port number} --target-port={target port number} --name {descriptive service name}
```

