FROM ubuntu:16.04

WORKDIR /app

RUN apt-get update && apt-get install -y ffmpeg wget python3-pip && \
    pip3 install --upgrade yle-dl && \
    rm -rf /var/lib/apt/lists/* 

ENTRYPOINT ["yle-dl"]
