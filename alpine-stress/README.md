# Alpine-Stress

This docker image takes the base alpine linux image and installs `stress` on it and then
removes all the dependencies used to compile `stress` from [source](http://people.seas.harvard.edu/~apw/stress/).
The final image only adds about ~1.5 MB to the standard ~4MB alpine image

### 1. Pull the image from docker hub

`docker pull deltaskelta/alpine-stress`

### 2. Run your stress command...

`docker run -it deltaskelta/alpine-stress stress --cpu 4`
