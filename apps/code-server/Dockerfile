FROM lscr.io/linuxserver/code-server:4.105.1

RUN apt-get update && \
    apt-get install -y curl ca-certificates gnupg && \
    curl -fsSL https://deb.nodesource.com/setup_22.x | bash - && \
    install -m 0755 -d /etc/apt/keyrings && \
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg && \
    chmod a+r /etc/apt/keyrings/docker.gpg && \
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu noble stable" > /etc/apt/sources.list.d/docker.list && \
    apt-get update && \
    apt-get install -y docker-ce-cli && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN echo 'export NVM_DIR="/home/kraddy/.nvm"' > /etc/profile.d/nvm.sh && \
    echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"' >> /etc/profile.d/nvm.sh && \
    echo '[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"' >> /etc/profile.d/nvm.sh && \
    chmod +x /etc/profile.d/nvm.sh

RUN mkdir -p /etc/cont-init.d && \
    echo '#!/bin/bash' > /etc/cont-init.d/40-docker-fix && \
    echo 'DOCKER_SOCK=/var/run/docker.sock' >> /etc/cont-init.d/40-docker-fix && \
    echo 'if [ -S "$DOCKER_SOCK" ]; then' >> /etc/cont-init.d/40-docker-fix && \
    echo '  DOCKER_GID=$(stat -c "%g" "$DOCKER_SOCK")' >> /etc/cont-init.d/40-docker-fix && \
    echo '  if ! getent group "$DOCKER_GID" >/dev/null 2>&1; then' >> /etc/cont-init.d/40-docker-fix && \
    echo '    groupadd -g "$DOCKER_GID" docker-host' >> /etc/cont-init.d/40-docker-fix && \
    echo '  fi' >> /etc/cont-init.d/40-docker-fix && \
    echo '  usermod -aG docker-host abc' >> /etc/cont-init.d/40-docker-fix && \
    echo 'fi' >> /etc/cont-init.d/40-docker-fix && \
    echo 'chown -R abc:abc /config/.local/share/opencode 2>/dev/null || true' >> /etc/cont-init.d/40-docker-fix && \
    chmod +x /etc/cont-init.d/40-docker-fix
