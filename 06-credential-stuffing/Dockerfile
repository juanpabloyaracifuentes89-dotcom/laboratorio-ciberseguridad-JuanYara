FROM alpine:latest

# Instalamos curl, bind-tools y python3
RUN apk add --no-cache curl bind-tools python3

WORKDIR /app

COPY entrypoint.sh /app/entrypoint.sh
RUN sed -i 's/\r$//' /app/entrypoint.sh && chmod +x /app/entrypoint.sh

EXPOSE 8080

ENTRYPOINT ["/bin/sh", "/app/entrypoint.sh"]
