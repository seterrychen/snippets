## Usage
### To build static file
```
GO111MODULE=on GOROOT=/usr/local/go go build -ldflags '-extldflags "-static"' ./cmd/drone-server
```
