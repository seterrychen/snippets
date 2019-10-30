## Installation
```
apt-get install -y ser2net
```

## Usage
### start daemon with config file
[config](https://github.com/I2SE/ser2net/blob/master/ser2net.conf)
```
# <TCP port>:<state>:<timeout>:<device>:<options>
2004:raw:5:/dev/ttyS3:115200
```

cmd
```
ser2net -c config
```


### How to connect to port which ser2net provided
```
$ sudo socat -d -d pty,link=/dev/vmodem0,waitslave tcp:IP:PORT
$ sudo minicom -D /dev/vmodem0
```
