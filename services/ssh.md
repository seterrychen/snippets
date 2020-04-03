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

### SSH tunnel
bind to remote ip:port 0.0.0.0:8080 to mapping local port 80
```
$ # -R [bind_address:]port:host:hostport
$ ssh -R 0.0.0.0:8080:localhost:80 -N root@example.com
```
Note that if you use OpenSSH sshd server, the server's GatewayPorts option needs to be enabled (set to yes or clientspecified) for this to work (check file /etc/ssh/sshd_config on the server).
