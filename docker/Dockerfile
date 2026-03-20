FROM node:20-bookworm

ENV DEBIAN_FRONTEND=noninteractive
ENV PATH="/root/google-cloud-sdk/bin:${PATH}"

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        bash \
        ca-certificates \
        curl \
        git \
        gnupg \
        python3 \
        python3-pip \
    && rm -rf /var/lib/apt/lists/*

RUN curl -fsSL https://sdk.cloud.google.com | bash -s -- --disable-prompts

RUN npm install -g @google/gemini-cli @googleworkspace/cli

WORKDIR /workspace

CMD ["bash"]
