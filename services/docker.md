# Installation
```
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
$ sudo usermod -aG docker your-user
```
[more](https://docs.docker.com/install/)

## Usage
### To clean docker logs
```
echo "" > $(docker inspect --format='{{.LogPath}}' <container_name_or_id>)
```

### How to Build and Run ARM Docker Images on x86 Hosts
Prepare
```
$ apt-get update && apt-get install -y --no-install-recommends qemu-user-static binfmt-support
$ update-binfmts --enable qemu-arm
$ docker run --rm --privileged multiarch/qemu-user-static:register
```

Build (inside Dockerfile)
```
COPY qemu-arm-static /usr/bin/qemu-arm-static
```

Run (if there is no qemu-arm-static inside image)
```
$ docker run -it --name your-container-name -v /usr/bin/qemu-arm-static:/usr/bin/qemu-arm-static your-arm-image
```

### Change storage path
ex: Debian/Ubuntu
```
FROM:
ExecStart=/usr/bin/docker daemon -H fd://
TO:
ExecStart=/usr/bin/docker daemon -g /new/path/docker -H fd://
```
```
