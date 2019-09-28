FROM node:alpine

ENV API_URL=http://localhost/api

WORKDIR /root
RUN apk add --no-cache git && \
    git clone https://github.com/ptuomola/frontend-example-docker.git && \
    mv frontend-example-docker/* . && \
    npm install && \
    apk del git && \ 
    adduser -D frontend && \ 
    chown -R frontend .

USER frontend

EXPOSE 5000
ENTRYPOINT ["npm", "start" ]
