## Usage
### Get Role name and credentials
```
$ curl http://169.254.169.254/latest/meta-data/iam/info   # get role name
$ curl http://169.254.169.254/latest/meta-data/iam/security-credentials/<role-name>  # get credential
```

### Get Region
```
$ curl --silent http://169.254.169.254/latest/dynamic/instance-identity/document
{
  "privateIp" : "172.31.2.15",
  "instanceId" : "i-12341ee8",
  "billingProducts" : null,
  "instanceType" : "t2.small",
  "accountId" : "1234567890",
  "pendingTime" : "2015-11-03T03:09:54Z",
  "imageId" : "ami-383c1956",
  "kernelId" : null,
  "ramdiskId" : null,
  "architecture" : "x86_64",
  "region" : "ap-northeast-1", # <- region
  "version" : "2010-08-31",
  "availabilityZone" : "ap-northeast-1c",
  "devpayProductCodes" : null
}
$ curl --silent http://169.254.169.254/latest/dynamic/instance-identity/document | jq -r .region
ap-northeast-1
```

### For docker container to access aws role
```
$ sudo sysctl -w net.ipv4.conf.all.route_localnet=1
$ sudo iptables -t nat -A PREROUTING -p tcp -d 169.254.170.2 --dport 80 -j DNAT --to-destination 127.0.0.1:51679
$ sudo iptables -t nat -A OUTPUT -d 169.254.170.2 -p tcp -m tcp --dport 80 -j REDIRECT --to-ports 51679
```
