# Linux concept

## Process
* [What Is a “Zombie Process” on Linux? - How-To Geek](https://www.howtogeek.com/119815/htg-explains-what-is-a-zombie-process-on-linux/)


## TTY
* [Linux TTY/PTS概述](https://segmentfault.com/a/1190000009082089)
* [Difference between pts and tty](https://unix.stackexchange.com/questions/21280/difference-between-pts-and-tty)


## IO
* [IO - 同步，异步，阻塞，非阻塞](https://blog.csdn.net/historyasamirror/article/details/5778378)


## SSH
* [SSH Host Key - What, Why, How | SSH.COM](https://www.ssh.com/ssh/host-key)


## Security Patch
```
$ sudo apt-get -s dist-upgrade | grep "^Inst" | grep -i securi # list packages which will be upgrded
$ sudo apt-get -s dist-upgrade | grep "^Inst" | grep -i securi | awk -F " " {'print $2'} | xargs sudo apt-get install
```

using `unattended-upgrade` will be better
```
$ sudo unattended-upgrade --dry-run -d
$ sudo unattended-upgrade -d
```
