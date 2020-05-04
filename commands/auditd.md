## Installation
$ apt install auditd

## Usage
```
example:
$ python run_forever.py &
[1] 24067
$ kill -9 24067

$ ausearch -sc kill
time->Mon Dec 25 19:52:55 2017
type=PROCTITLE msg=audit(1514202775.088:351): proctitle="bash"
type=OBJ_PID msg=audit(1514202775.088:351): opid=24067 日uid=-1 ouid=3010 oses=-1 ocomm="python"
type=SYSCALL msg=audit(1514202775.088:351): arch=c000003e syscall=62 success=yes exit=0 a0=5e03 a1=9 a2=0 a3=7ffc0d9f7b90 items=0 ppid=1349 pid=1350  uid=3010 gid=3010 euid=3010 suid=3010 fsuid=3010 egid=3010 sgid=3010 fsgid=3010 tty=pts0 comm="bash" exe="/bin/bash" key=(null)
```

## Reference
* [我的进程去哪儿了，谁杀了我的进程- xybaby - 博客园](https://www.cnblogs.com/xybaby/p/8098229.html)
