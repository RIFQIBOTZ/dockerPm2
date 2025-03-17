FROM        node:20-bullseye-slim

LABEL       author="RIFQII STORE" maintainer="rifqiistore87@gmail.com"

RUN         apt update \
            && apt -y install ffmpeg iproute2 git sqlite3 libsqlite3-dev python3 python3-dev ca-certificates dnsutils tzdata zip tar curl build-essential libtool iputils-ping \
            && useradd -m -d /home/container container

# Update NPM ke versi terbaru
RUN         npm install npm@latest -g

# Install PM2 versi terbaru secara global
RUN         npm install pm2@latest -g

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

# Copy entrypoint script
COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]