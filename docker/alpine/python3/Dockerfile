
FROM golang:1.19.0-alpine3.16 as builder
RUN apk update && apk upgrade && apk add git
RUN git clone --depth 1 --branch v0.1.1  https://github.com/Ignalina/thund-cli.git && cd thund-cli && go build

FROM python:3.10.6-alpine3.16
COPY --from=builder /go/thund-cli/thund-cli /

RUN echo "http://dl-cdn.alpinelinux.org/alpine/latest-stable/main" > /etc/apk/repositories
RUN echo "http://dl-cdn.alpinelinux.org/alpine/latest-stable/community" >> /etc/apk/repositories
RUN apk add --upgrade apache-arrow py3-apache-arrow gcc gfortran build-base wget freetype-dev libpng-dev openblas-dev


ENV HOME=/home/brokkr

RUN addgroup -g 1000 thund && adduser -u 1000 -G thund -h $HOME -D brokkr && ls -lR /home/

RUN pip3 install --upgrade pip

USER brokkr
WORKDIR /home/brokkr
RUN pip3 install numpy
CMD /thund-cli streamcmd .
