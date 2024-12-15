# Этап сборки
FROM golang:1.20-alpine AS builder
WORKDIR /app
COPY . .
RUN go mod tidy && go build -o bot .

# Этап запуска
FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/bot .
ENV TELEGRAM_BOT_TOKEN=${TELEGRAM_BOT_TOKEN}
CMD ["./bot"]
