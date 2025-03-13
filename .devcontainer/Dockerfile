FROM mcr.microsoft.com/devcontainers/javascript-node:22

# Install additional packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    git \
    curl \
    wget \
    vim \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Set up global npm packages
RUN npm install -g zenn-cli@latest

# Set up working directory
WORKDIR /workspace

# Set up user
USER node

# Add Zenn CLI to path
ENV PATH="/workspace/node_modules/.bin:${PATH}"