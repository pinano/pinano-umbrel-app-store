FROM ghcr.io/mxpv/podsync:latest

USER root

# Instalar nodejs para resolver los desafíos de JavaScript (n-challenge) de YouTube en Alpine ARM64
RUN apk add --no-cache nodejs

# Configurar yt-dlp para que use Node.js automáticamente
RUN mkdir -p /etc/yt-dlp && echo "--js-runtimes node" > /etc/yt-dlp/config
