FROM ubuntu:16.04
WORKDIR /root
RUN apt-get update && apt-get install -y git curl
RUN git clone https://github.com/docker-hy/backend-example-docker 
WORKDIR /root/backend-example-docker
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
RUN npm install
ENV FRONT_URL=http://localhost:5000
EXPOSE 8000
ENTRYPOINT ["/usr/bin/npm", "start"]
