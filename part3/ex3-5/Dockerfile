FROM node:alpine as build-stage

ENV API_URL=http://localhost/api

WORKDIR /root
RUN apk add --no-cache git && \
    git clone https://github.com/ptuomola/frontend-example-docker.git && \
    mv frontend-example-docker/* . && \
    npm install && \
    apk del git && \ 
    npm run build 

FROM node:alpine

WORKDIR /root

COPY --from=build-stage /root/dist/ /root/dist

RUN npm install -g serve && \
    adduser -D frontend && \ 
    chown -R frontend .

USER frontend

EXPOSE 5000
ENTRYPOINT ["serve", "-s", "-l", "5000", "dist" ]
