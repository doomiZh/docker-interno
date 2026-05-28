FROM docker.n8n.io/n8nio/n8n:latest

USER root

# 1. Docker CLI — binario estático
RUN wget -qO /tmp/docker.tgz \
     "https://download.docker.com/linux/static/stable/x86_64/docker-27.3.1.tgz" \
&& tar xzf /tmp/docker.tgz \
     --strip-components=1 \
     -C /usr/local/bin \
     docker/docker \
&& chmod +x /usr/local/bin/docker \
&& rm /tmp/docker.tgz

# 2. Docker Compose v2 — plugin independiente
RUN mkdir -p /usr/local/lib/docker/cli-plugins \
&& wget -qO /usr/local/lib/docker/cli-plugins/docker-compose \
     "https://github.com/docker/compose/releases/download/v2.29.7/docker-compose-linux-x86_64" \
&& chmod +x /usr/local/lib/docker/cli-plugins/docker-compose

USER node