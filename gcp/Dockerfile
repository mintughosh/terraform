FROM hashicorp/terraform:latest

# Install dependencies
RUN apk add --no-cache \
    curl \
    unzip \
    jq \
    git \
    bash \
    python3 \
    py3-pip \
    openssh-client

# Install HashiCorp Vault
RUN curl -fsSL https://releases.hashicorp.com/vault/1.13.3/vault_1.13.3_linux_amd64.zip -o vault.zip \
    && unzip vault.zip \
    && mv vault /usr/local/bin/ \
    && rm vault.zip

# Install Google Cloud SDK
RUN curl -sSL https://sdk.cloud.google.com | bash -s -- --install-dir=/usr/local/gcloud --disable-prompts
ENV PATH="/usr/local/gcloud/google-cloud-sdk/bin:$PATH"

# Set working directory
WORKDIR /infra

ENTRYPOINT ["/bin/bash"]
