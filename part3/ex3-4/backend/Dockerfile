FROM node:alpine

ENV FRONT_URL=http://localhost

WORKDIR /app

#RUN apt-get update && apt-get install -y git curl && \
RUN apk add --no-cache git && git clone https://github.com/docker-hy/backend-example-docker && \
    apk del git && \
    adduser -D backend && \
    chown -R backend backend-example-docker

USER backend

WORKDIR /app/backend-example-docker
RUN npm install

EXPOSE 8000
ENTRYPOINT ["npm", "start"]
