FROM git.zarantonello.dev/infra/ci:v1.0.12@sha256:20437994071182eae60b0be8e529eb70da8822f9fc28e4b22540f58f5b4de558

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
