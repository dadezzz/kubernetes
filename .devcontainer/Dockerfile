FROM git.zarantonello.dev/infra/ci:v1.1.0@sha256:4857e05360663c5f4351a119debbe0f2d556d334982faaf6bf4ef38285c95037

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
