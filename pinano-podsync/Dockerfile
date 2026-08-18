FROM ghcr.io/mxpv/podsync:latest

USER root

# Instalar Deno, Python3, ffmpeg, curl y certificados
RUN apk add --no-cache deno python3 ffmpeg ca-certificates curl

# Descargar el binario oficial de yt-dlp y colocarlo directamente como youtube-dl y yt-dlp
RUN curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/youtube-dl && \
    chmod a+rx /usr/local/bin/youtube-dl && \
    cp /usr/local/bin/youtube-dl /usr/bin/youtube-dl && \
    cp /usr/local/bin/youtube-dl /usr/local/bin/yt-dlp && \
    cp /usr/local/bin/youtube-dl /usr/bin/yt-dlp && \
    chmod a+rx /usr/local/bin/youtube-dl /usr/bin/youtube-dl /usr/local/bin/yt-dlp /usr/bin/yt-dlp

# Asegurarse de que no existan configs obsoletas
RUN rm -rf /etc/yt-dlp
