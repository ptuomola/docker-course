FROM ubuntu:16.04

ENV API_URL=http://localhost/api

WORKDIR /root
RUN apt-get update && apt-get install -y curl git && \
    git clone https://github.com/ptuomola/frontend-example-docker.git && \
    mv frontend-example-docker/* . && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    npm install && \
    apt-get purge -y --auto-remove curl git && \ 
    rm -rf /var/lib/apt/lists/* && \
    useradd -m frontend && \ 
    chown -R frontend .

USER frontend

EXPOSE 5000
ENTRYPOINT ["/usr/bin/npm", "start" ]
