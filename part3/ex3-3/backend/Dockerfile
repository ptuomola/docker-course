FROM ubuntu:16.04

ENV FRONT_URL=http://localhost

WORKDIR /app

RUN apt-get update && apt-get install -y git curl && \
    git clone https://github.com/docker-hy/backend-example-docker && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \ 
    apt-get install -y nodejs && \
    apt-get purge -y --auto-remove curl git && \ 
    rm -rf /var/lib/apt/lists/* && \
    useradd -m backend && \
    chown -R backend backend-example-docker

USER backend

WORKDIR /app/backend-example-docker
RUN npm install

EXPOSE 8000
ENTRYPOINT ["/usr/bin/npm", "start"]
