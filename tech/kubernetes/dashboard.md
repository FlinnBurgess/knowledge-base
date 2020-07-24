# Dashboard

The kubernetes Dashboard UI is a web UI which runs on the kubernetes master\(s\). It is accessible if you have direct access to the kubernetes cluster that your application runs on, which is unlikely in a production system. However, there is a way around this:

```text
kubectl proxy
```

This command creates a proxy for you in situations where you do not have direct access to the cluster.

The UI allows you to do many of the things you can do using `kubectl`, but supplies a GUI alongside it. This does however make it a little less flexible than the CLI.

The best way to access the UI is to run the above command, then navigate to [http://localhost:8001/api/v1/namespaces/kube-system/services/kubernetes-dashboard/proxy](http://localhost:8001/api/v1/namespaces/kube-system/services/kubernetes-dashboard/proxy) in your browser.

