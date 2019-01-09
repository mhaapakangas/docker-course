FROM ubuntu:16.04

RUN apt-get update && \
  apt-get install -y python3 python3-pip wget ffmpeg && \
  pip3 install --prefix /usr/local --upgrade --no-cache-dir pycrypto yle-dl && \
  rm -rf /var/lib/apt/lists/*

WORKDIR /videos
ENTRYPOINT ["/usr/local/bin/yle-dl"]
