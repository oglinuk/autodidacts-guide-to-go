FROM alpine:latest
RUN apk update && apk add go \
	vim
COPY README.md main.go /src/
WORKDIR /src
