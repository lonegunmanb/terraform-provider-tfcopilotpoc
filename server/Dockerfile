FROM golang:1.22.2 as builder
COPY . /src
WORKDIR /src
RUN  CGO_ENABLED=0 go build server

FROM alpine:latest as rnner
COPY --from=builder /src/server /server

ENTRYPOINT ["/server"]