## List all API resources
```bash=
$ kubectl api-resources # Print the supported API resources on the server
```

## Cluster info
```bash
$ kubectl cluster-info                                                   
Kubernetes master is running at https://192.168.99.101:8443
KubeDNS is running at https://192.168.99.101:8443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
```
```bash=
$ kubectl get no      # to list all nodes of current cluster, no => nodes
$ kubectl describe no # to show detail nodes information of current cluster
```

## Pods & Deployments

* Create a Pod by Deployment
```bash=
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10
```

* Get info of Pod & Deployment
```bash=
$ kubectl get po          # to list all pods, po => pods
$ kubectl describe po     # to show detail pods information
$ kubectl get deploy      # to list deployments, deploy => deployments
$ kubectl describe deploy # to show detail deployments
```
