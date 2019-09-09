FROM ubuntu:latest
RUN apt-get update && apt-get install -y git && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get install -y nodejs
RUN node -v && npm -v
RUN git clone https://github.com/ptuomola/node-hello-world.git
WORKDIR node-hello-world
EXPOSE 3000
ENTRYPOINT ["node", "src/server.js"] 
