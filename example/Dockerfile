FROM ubuntu:latest

RUN apt update -y
RUN apt install -y sudo build-essential

WORKDIR /root
ADD main.c .
RUN gcc main.c

LABEL docker-script.export="/root/a.out"
