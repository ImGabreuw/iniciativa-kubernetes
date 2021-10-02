FROM golang:1.7-alpine3.6

WORKDIR /app

COPY main.go .

RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main

CMD ["./main"]