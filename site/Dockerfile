# Этап сборки
FROM golang:1.20-alpine AS builder
WORKDIR /app
COPY . .
RUN go mod tidy && go build -o site .

# Этап запуска
FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/site .
COPY static ./static
CMD ["./site"]
