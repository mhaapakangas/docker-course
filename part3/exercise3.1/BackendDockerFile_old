FROM ubuntu:16.04

WORKDIR /myDir
RUN apt-get update && apt-get install -y git curl
RUN git clone https://github.com/docker-hy/backend-example-docker.git 

WORKDIR /myDir/backend-example-docker
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs

RUN npm install
EXPOSE 8000

CMD ["/usr/bin/npm", "start"]
