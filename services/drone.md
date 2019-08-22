## Usage
### Pull private images with 1.0
```
$ # you would pass path and mount the config file into your `agent` container
$ docker run -v /root/.docker/config.json:/root/.docker/config.json \
             -e DRONE_DOCKER_CONFIG=/root/.docker/config.json
```
