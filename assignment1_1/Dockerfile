FROM golang:1.20 AS builder
WORKDIR /app
COPY go.mod . 
RUN go mod tidy
COPY main.go .
RUN go build -o hello

FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/hello .
ENTRYPOINT ["./hello"]
