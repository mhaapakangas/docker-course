FROM alpine:3.7 

RUN apk update && apk upgrade && \
  apk add --no-cache py2-pip py-crypto wget ffmpeg gcc musl-dev libxslt-dev libxml2-dev py-lxml python2-dev && \
  pip install --upgrade pip yle-dl && \
  apk del gcc musl-dev libxslt-dev libxml2-dev python2-dev && \
  adduser -D app

USER app

WORKDIR /videos

ENTRYPOINT ["yle-dl"]
