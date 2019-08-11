## Install

Alpine: `inotify-tools`
Debian: `inotify-tools`


## Usage
```
#!/bin/sh
       
while inotifywait -e modify /var/log/messages; do
    if tail -n1 /var/log/messages | grep httpd; then
        kdialog --msgbox "Apache needs love!"
    fi
done
```

* `-e`: event, like access, modify and open ... etc

Reference: https://linux.die.net/man/1/inotifywait
