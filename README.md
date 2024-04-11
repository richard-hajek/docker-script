# Docker Script

## Pitch

Dockerfiles are universal scripts, but what if you want use a Dockerfile to generate / build something? This project allows you to!

## Install

Clone this repository and copy 'docker-script' to your preferred $PATH.

## Quickstart

Take any Dockerfile, and add label `docker-script.export` with path to what you want exported from the image, for example

```Dockerfile
FROM ubuntu:latest

RUN apt update -y
RUN apt install -y sudo build-essential

WORKDIR /root
ADD main.c .
RUN gcc main.c

LABEL docker-script.export="/root/a.out"
```

Running `docker-script` in this directory will build the Dockerfile, the app, and automatically extracts the compiled program! Which will be available in $PWD/a.out.
