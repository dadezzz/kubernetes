FROM git.zarantonello.dev/infra/ci:v1.1.23@sha256:167af5044e7365a3eb7f6964afc37979855ed4cd6df893d66781a941e07be423

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.4@sha256:b9e4f7c6bc0f92615d8b0c8376afa725f0f6a64f45593b4318ae1c125d4f4ac3 /usr/local/bin/flux /usr/local/bin/
