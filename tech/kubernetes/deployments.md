# Deployments

A deployment is a high-level object typically described in a YAML file, used to describe the containers/pods we are interested in, how they work together, and the policy for caring for those pods. In other words, a deployment defines the desired state of an application.

Here is an example `deployment.yaml`

```yaml
apiVersion: apps/v1beta2
kind: Deployment
metadata:
  name: tomcat-deployment
spec:
  selector:
    matchLabels:
      app: tomcat
  replicas: 1
  template:
    metadata:
      labels:
        app: tomcat
    spec:
      containers:
      - name: tomcat
        image: tomcat:9.0
        ports:
        - containerPort: 8080
```

`name: tomcat-deployment` describes the name of the deploment. `replicas: 1` ensures that there is only a single replica of the deployment \(i.e. 1 instance of 1 docker image\). `image: tomcat:9.0` defines the image to be used by the deployment. If we don't specify a repository to use, kubernetes will default to public Docker Hub. `- containerPort: 8080` tells us that we the deployment exposes a port 8080.

### nodeSelector

nodeSelector is a property on a deployment that uses labels and selectors to choose which nodes the master decides to run a given pod on.

To add a nodeSelector to a deployment, under `spec` in `deployment.yaml`, we add a `nodeSelector` field, with the labels that we want to select by:

```yaml
spec:
    containers:
        ....
    nodeSelector:
        {label key}: {label value}
```

This tells kubernetes that when it is looking for nodes to deploy that deployment onto, it should look for a label on the node with the given key and value pair.

### Applying the deployment

To apply the deployment specified in our `deployment.yaml` to our cluster, we run the command

```text
kubectl apply -f {path to deployment.yaml}
```

### Listing deployments

```text
kubectl get deployments
```

### Viewing status of deployment rollouts

```text
kubectl rollout status deployment {deployment name}
```

### Setting the image of a deployment

```text
kubectl set image deployment/{deployment name} {container naem}={image name}:{image tag}
```

### Viewing the history of a rollout, including previous versions

\`\`\` kubectl rollout history deployment/{deployment name}

