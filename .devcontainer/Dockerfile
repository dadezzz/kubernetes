FROM git.zarantonello.dev/infra/ci:v1.0.13@sha256:343459e421c2ab394f1891586af0d7cfc21017f1f3a52fcc42878cac557a86e2

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
