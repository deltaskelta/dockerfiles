# Golang Documentation In a Container

This Dockerfile runs the golang documentation on a docker host, and will restart
always so that the documentation will always be available locally. 

*NOTE:* If you are on OSX or windows, the binaries mounted from your $GOPATH will be
compiled for a different machine and therefore will not work on the linux virtual
machine. 

*NOTE:* when the container starts, the godoc binary (from golang root install) needs to
parse all the local packages that are in the src directory, therefore, depending on
the size of your $GOPATH/src directory, it may take a few miinutes to startup.

### 1. Pull the image from docker hub

`docker pull deltaskelta/go-docs`

### 2. Run the container

```bash
docker run \
    --restart always \
    -itdp 8001:80 \
    -v $GOPATH:/go \
    deltaskelta/go-doc
```
