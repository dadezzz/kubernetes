FROM git.zarantonello.dev/infra/ci:v1.1.8@sha256:f1fe69b7681b2a0da89ea4cab8c8b47f5729c25c9e763f897806eaf25b06aad3

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
