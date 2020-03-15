## Installation
### Standalone
```
docker run -d -p 4444:4444 -v /dev/shm:/dev/shm selenium/standalone-firefox:3.141.59-zirconium
```

### Debugging with VNC
```
docker run -d -P -p <port4VNC>:5900 --link selenium-hub:hub -v /dev/shm:/dev/shm selenium/node-firefox-debug:3.141.59-zirconium
```
