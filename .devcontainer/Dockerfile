FROM git.zarantonello.dev/infra/ci:v1.1.1@sha256:d8b909dc9603e6e965156c06f9cc6e674b73c7a5cbc14897551254fc30f8af2c

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
