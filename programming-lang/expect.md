## Installation
```
apt-get install expect
apk add expect
```

## Usage
* [expect(1) - Linux man page - Linux Documentation - Die.net](https://linux.die.net/man/1/expect)
* [Basic principles of using tcl-expect scripts - gists · GitHub](https://gist.github.com/Fluidbyte/6294378)


### trap
trap [[command] signals]

```
trap exit {SIGINT SIGTERM}
```

or

```
proc do_something {} {
   do_something
   exit
}

trap func {SIGNAL}
```

### get spawned prcoess id
```
spawn ssh name@host
set pid [exp_pid]
puts "PID: $pid"
```

