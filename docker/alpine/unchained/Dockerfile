FROM rust:1.63-alpine3.16 as rustbuilder
RUN apk add wget bash git rust-wasm

FROM golang:1.19.0-alpine3.16  as gobuilder
RUN apk update && apk upgrade && apk add git apache-arrow
RUN git clone --depth 1 --branch v0.1.1  https://github.com/Ignalina/thund-cli.git && cd thund-cli && go build
CMD /go/thund-cli/thund-cli streamcmd .
