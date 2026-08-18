FROM ghcr.io/mxpv/podsync:latest

USER root

# Instalar Node.js, Python3, curl y certificados
RUN apk add --no-cache nodejs curl ca-certificates python3

# Descargar la versión más reciente de yt-dlp y enlazarla a youtube-dl
RUN curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/youtube-dl && \
    chmod a+rx /usr/local/bin/youtube-dl && \
    ln -sf /usr/local/bin/youtube-dl /usr/bin/youtube-dl && \
    ln -sf /usr/local/bin/youtube-dl /usr/local/bin/yt-dlp && \
    ln -sf /usr/local/bin/youtube-dl /usr/bin/yt-dlp

# Configurar yt-dlp para que use Node.js automáticamente como JS runtime
RUN mkdir -p /etc/yt-dlp && echo "--js-runtimes node" > /etc/yt-dlp/config
