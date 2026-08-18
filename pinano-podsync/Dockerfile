FROM ghcr.io/mxpv/podsync:latest

USER root

# Instalar Node.js, Python3, ffmpeg, curl y certificados desde repositorios oficiales de Alpine
RUN apk add --no-cache nodejs python3 ffmpeg ca-certificates curl

# Descargar el binario oficial y más reciente de yt-dlp
RUN curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/youtube-dl && \
    chmod a+rx /usr/local/bin/youtube-dl && \
    cp /usr/local/bin/youtube-dl /usr/bin/youtube-dl && \
    cp /usr/local/bin/youtube-dl /usr/local/bin/yt-dlp && \
    cp /usr/local/bin/youtube-dl /usr/bin/yt-dlp && \
    chmod a+rx /usr/local/bin/youtube-dl /usr/bin/youtube-dl /usr/local/bin/yt-dlp /usr/bin/yt-dlp

# Configurar yt-dlp para que use Node.js automáticamente como JS runtime
RUN mkdir -p /etc/yt-dlp && \
    echo "--js-runtimes node" > /etc/yt-dlp/config && \
    echo "--js-runtimes node" > /etc/yt-dlp.conf
