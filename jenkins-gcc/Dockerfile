# This image is based off the latest Jenkins LTS
FROM jenkins/jenkins:lts-alpine

ENV http_proxy=http://127.0.0.1:8118

USER root

# Add the docker binary so running Docker commands from the master works nicely
RUN apk -U add docker

RUN apk -U add go

RUN apk -U add build-base

RUN apk add --no-cache -U alpine-sdk 

#RUN apk add --no-cache --virtual .build-deps bash gcc musl-dev openssl go
#RUN wget -O go.tgz https://golang.org/dl/go1.14.4.src.tar.gz && tar -C /usr/local -xzf go.tgz
#RUN cd /usr/local/go/src/ && ./make.bash && apk del .build-deps

USER jenkins

RUN install-plugins.sh antisamy-markup-formatter matrix-auth blueocean:$BLUEOCEAN_VERSION
