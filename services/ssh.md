## Install
### Daemon
```
$ # Debain
$ apt-get install openssh-server
```

### Client
```
$ # Debian
$ apt-get install openssh-client
```


## Usage
### disable host key checking (client)
```
$ ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null 192.168.0.110
```
