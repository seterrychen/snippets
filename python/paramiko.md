## Installation
```
pip install paramiko
```

## Usage
### using private key to ssh
```
import paramiko

k = paramiko.RSAKey.from_private_key_file("/Users/whatever/Downloads/mykey.pem")
c = paramiko.SSHClient()
c.set_missing_host_key_policy(paramiko.AutoAddPolicy())
c.connect(hostname = "www.acme.com", username = "ubuntu", pkey = k)
c.exec_command("cmd_string")
```
