FROM alpine:latest

RUN apk add --no-cache curl python3

WORKDIR /app

# Simulamos la descarga de una dependencia maliciosa en la cadena de suministro
RUN echo "echo '[PAYLOAD ADVERSARIO] Dependencia maliciosa ejecutÃ¡ndose con privilegios del contenedor...'" > /app/malicious_dependency.sh && \
    chmod +x /app/malicious_dependency.sh

COPY entrypoint.sh /app/entrypoint.sh
RUN sed -i 's/\r$//' /app/entrypoint.sh && chmod +x /app/entrypoint.sh

EXPOSE 8080

ENTRYPOINT ["/bin/sh", "/app/entrypoint.sh"]
