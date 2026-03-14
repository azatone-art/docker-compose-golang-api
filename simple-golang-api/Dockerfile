FROM golang:1.25.7-alpine3.23 AS builder

WORKDIR /build

COPY main.go go.mod go.sum ./

# Сборка бинарного файла main
RUN go build -o main main.go


FROM alpine:3.23

WORKDIR /app

#RUN apk --no-cache add ca-certificates

COPY --from=builder /build/main .

EXPOSE 8080

CMD ["./main"] 
