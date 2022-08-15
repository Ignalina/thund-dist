FROM golang:1.19.0-alpine3.16
RUN apk update && apk upgrade && apk add git apache-arrow
RUN git clone https://github.com/Ignalina/thund-cli.git && cd thund-cli && go build

CMD /go/thund-cli/thund-cli streamcmd .
