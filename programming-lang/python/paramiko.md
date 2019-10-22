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
c.connect(hostname="www.acme.com", username="ubuntu", pkey= k)
c.exec_command("cmd_string")
```


### execute command
```
c = paramiko.SSHClient()
c.set_missing_host_key_policy(paramiko.AutoAddPolicy())
c.connect(hostname=host, username=name)
stdin, stdout, stderr = c.exec_command('cmd')  # result will be bytes Python3
c.close()
```


### using sftp to upload file
```
t = paramiko.Transport((host, 22))
t.connect(username=user, password=password)
sftp = paramiko.SFTPClient.from_transport(t)
sftp.put('/local_path/filename', '/remote_path/filename')
sftp.close()
t.close()
```
