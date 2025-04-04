FROM codercom/code-server:latest

# Switch to root for installation
USER root

# Install additional dependencies as needed
RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    python3 \
    python3-pip \
    gnupg \
    --no-install-recommends \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install Node.js and Yarn (required for Backstage)
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get update && \
    apt-get install -y nodejs && \
    npm install -g yarn

# Install global extensions for code-server
RUN code-server --install-extension ms-python.python \
    && code-server --install-extension ms-toolsai.jupyter \
    && code-server --install-extension dbaeumer.vscode-eslint \
    && code-server --install-extension saoudrizwan.claude-dev

# Set up the workspace directory
WORKDIR /workspace

# Set the default command to run code-server
CMD ["code-server", "--bind-addr", "0.0.0.0:8080", "--auth", "none", "."] 