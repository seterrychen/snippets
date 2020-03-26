## Installation
```
brew install helm
```

## Usage
### install chart
```
helm install -n services testlink \
  --set testlinkUsername=ccc \
  --set image.tag=1.9.19-debian-9-r294 \
  --set xxxxx=xxxx
  bitnami/testlink
```
