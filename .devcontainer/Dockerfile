FROM git.zarantonello.dev/infra/ci:v1.0.11@sha256:0392925655dce34e979ff5e03f5dc12ec9bfb155ef048ca17fe0f36a754378de

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
