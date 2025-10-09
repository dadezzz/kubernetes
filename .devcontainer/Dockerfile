FROM git.zarantonello.dev/infra/ci:v1.0.8@sha256:b67f727662fc1f896e564b8f43e1c06465a298fbe0510945fa7348a56d3b9ffc

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
