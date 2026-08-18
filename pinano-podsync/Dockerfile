FROM ghcr.io/mxpv/podsync:latest

USER root

# Instalar Deno (runtime de JS nativo de yt-dlp), Python3, pip, ffmpeg y certificados
RUN apk add --no-cache deno python3 py3-pip ffmpeg ca-certificates curl

# Instalar la versión completa de yt-dlp con componentes EJS
RUN pip3 install --break-system-packages --upgrade "yt-dlp[default]"

# Enlazar el binario para Podsync
RUN ln -sf $(which yt-dlp) /usr/local/bin/youtube-dl && \
    ln -sf $(which yt-dlp) /usr/bin/youtube-dl && \
    ln -sf $(which yt-dlp) /usr/local/bin/yt-dlp && \
    ln -sf $(which yt-dlp) /usr/bin/yt-dlp

# Limpiar cualquier config previa para que use Deno por defecto
RUN rm -rf /etc/yt-dlp
