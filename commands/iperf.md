## Usage
```
$ # server mode
$ docker run  -it --rm --name=iperf3-server -p 5201:5201 networkstatic/iperf3 -s
$ # client mode
$ docker run  -it --rm networkstatic/iperf3 -c server_ip
```
