# Setup local Kubernetes Cluster using Minikube
## Installation (MacOS)

1. Install kubectl (version `v1.14.0`)

   ```bash=
   curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.14.0/bin/darwin/amd64/kubectl
   chmod +x ./kubectl
   sudo mv ./kubectl /usr/local/bin/kubectl
   kubectl version # test kubectl
   ```

2. Install a hypervisor 

   Using [Virtualbox](https://www.virtualbox.org/wiki/Downloads)

3. Install Minikube

   ```bash=
   brew install minikube
   ```

## Start minikube cluster

```bash=
minikube start --vm-driver=virtualbox --kubernetes-version=v1.14.0

--vm-driver           will auto be detected if you not specify
--kubernetes-version  default value is decided by minikube
```

This command creates and configures a Virtual Machine that runs a single-node Kubernetes cluster. This command also configures your kubectl installation to communicate with this cluster.

Note：To make sure that kubectl version is same with kubernetes for compatible

