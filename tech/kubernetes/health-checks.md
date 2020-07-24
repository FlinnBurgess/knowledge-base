# Health Checks

Kubernetes uses health checks to ascertain the status of a Pod. There are two types of health check:

### Readiness probes

To determine when a Pod is "ready", i.e. when a container has loaded everything that it needs to begin execution of commands.

### Liveness probes

Once a Pod is ready, liveness probes check whether that Pod is "healthy" or "unhealthy".

In both types of probe, there are a couple of ways of ascertaining the status of the pod:

* Making a successful HTTP/TCP request to the Pod
* Successfully running a command on the Pod

Probes are defined in the container specifcation for a Pod or Deployment.

### Defining probes

The following is an example of defining a readiness and liveness probe inside the `deployment.yaml` file \(see [Deployments](:/80511e6ee89943dab1577d8514f64ed2)\). The definition goes under `containers` in `spec`:

```yaml
spec:
    containers:
    - name: {name}
      .....
      livenessProbe:
        httpGet:
            path: /
            port: 8080
        initialDelaySeconds: 30
        periodSeconds: 30
      readinessProbe:
        httpGet:
            path: /
            port: 8080
        initialDelaySeconds: 15
        periodSeconds: 3
```

Here we define the two probes as simple HTTP requests on the / directory. The readiness probe waits 15 seconds before probing every 3 seconds.

Once the pod has been confirmed as "ready", the liveness probe will begin probing every 30 seconds with another HTTP request to determine if the pod is live. If this request fails, the Pod is deemed to be unhealthy, otherwise it is deemed to be healthy.

