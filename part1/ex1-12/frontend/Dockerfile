FROM ubuntu:16.04
WORKDIR /root
RUN apt-get update && apt-get install -y curl && apt-get install -y git
RUN git clone https://github.com/ptuomola/frontend-example-docker.git  
RUN mv frontend-example-docker/* .
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
RUN node -v && npm -v
RUN npm install
ENV API_URL=http://192.168.99.107:8000/
EXPOSE 5000
ENTRYPOINT ["/usr/bin/npm", "start" ]
