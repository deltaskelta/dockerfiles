# DESCRIPTION:  Run a minimal (~5mb) `stress` binary
# AUTHOR:       Jeff Willette <jrwillette88@gmail.com>
# COMMENTS:
#
#   This dockerfile will build a stress binary and then remove the entire build toolchain
#   in order to keep the image small. 
#
# USAGE:
#
#	# Download the Dockerfile
#	wget https://raw.githubusercontent.com/deltaskelta/dockerfiles/master/alpine-stress/Dockerfile
#
#	# Build gparted image
#	docker build -t alpine-stress .
#
#   docker run -it \
#        deltaskelta/alpine-stress \
#        stress --cpu 4`
#
FROM alpine:latest

RUN apk add --update gcc g++ make && \
    wget http://people.seas.harvard.edu/~apw/stress/stress-1.0.4.tar.gz && \
    tar -xf stress-1.0.4.tar.gz && \
    cd stress-1.0.4 && \
    ./configure && \
    make && \
    make install && \
    cd / && \
    rm stress-1.0.4.tar.gz && \
    rm -r stress-1.0.4/ && \
    apk del gcc g++ make
