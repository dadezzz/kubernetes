FROM git.zarantonello.dev/infra/ci:v1.1.2@sha256:a15653b8d9530e0ae6cd59453c772106fa0d3da8bb763e8fdd7f3fbce24c7e0a

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
