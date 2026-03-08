FROM golang:1.26.1-alpine3.23 as builder

WORKDIR /app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY go.mod go.sum ./
RUN go mod download

COPY . .

RUN go build -o magic-stream-server .

FROM scratch

COPY --from=builder /app/magic-stream-server /magic-stream-server

EXPOSE 8080

CMD ["./magic-stream-server"]
