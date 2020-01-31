# Run Kubernetes on Amazon EKS service
## Tools

* `awscli` : [Document](https://docs.aws.amazon.com/cli/index.html), eksctl prerequisites, pip intall awscli
* `eksctl` : [Document](https://eksctl.io/)


## Using eksctl to create EKS cluster

```bash
$ eksctl create cluster \                                             
--name prod \
--version 1.14 \
--nodegroup-name standard-workers \
--node-type t3.medium \
--nodes 2 \
--nodes-min 1 \
--nodes-max 4
```


## for other IAM user to control kubernetes

Reference: [Managing Users or IAM Roles for your Cluster](https://docs.aws.amazon.com/en_us/eks/latest/userguide/add-user-role.html)

After using eksctl creating cluster and work nodes, kubernetes will has ConfigMap `aws-auth`, you can put your `user` into the ConfigMap. Default config has kubernetes worker nodes to access master node.


```bash
$ kubectl -n kube-system edit cm aws-auth
apiVersion: v1
data:
  mapRoles: |
    - rolearn: arn:aws:iam::111122223333:role/doc-test-worker-nodes-NodeInstanceRole-WDO5P42N3ETB
      username: system:node:{{EC2PrivateDNSName}}
      groups:
        - system:bootstrappers
        - system:nodes
  mapUsers: |
    - userarn: arn:aws:iam::555555555555:user/admin
      username: admin
      groups:
        - system:masters
```


## References

* [EKS Platform Versions](https://docs.aws.amazon.com/eks/latest/userguide/platform-versions.html)
