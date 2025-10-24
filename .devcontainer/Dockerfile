FROM git.zarantonello.dev/infra/ci:v1.1.7@sha256:bbcba3289d1ba2c1a9ad94839104bdad0b03ab885d3284e5e6f84750e99265b7

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
