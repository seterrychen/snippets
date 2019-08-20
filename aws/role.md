## Usage
### Get Role name and credentials
```
$ curl http://169.254.169.254/latest/meta-data/iam/info   # get role name
$ curl http://169.254.169.254/latest/meta-data/iam/security-credentials/<role-name>  # get credential
```
