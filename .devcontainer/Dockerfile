FROM git.zarantonello.dev/infra/ci:v1.1.9@sha256:8d13f82f8ff99b206c2a33eee0a4bb37affdf5a55743c819b9ed75be929233d7

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
