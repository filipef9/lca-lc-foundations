FROM mcr.microsoft.com/devcontainers/python:3.13

ENV DEBIAN_FRONTEND=noninteractive

RUN set -eux; \
    curl -fsSL https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --dearmor -o /etc/apt/keyrings/yarn.gpg; \
    echo "deb [signed-by=/etc/apt/keyrings/yarn.gpg] https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list; \
    apt-get update; \
    apt-get install -y --no-install-recommends yarn; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/*

# Install system dependencies for PortAudio
RUN apt-get update && apt-get install -y \
    libportaudio2 \
    libasound-dev \
    && rm -rf /var/lib/apt/lists/*