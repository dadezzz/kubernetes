FROM git.zarantonello.dev/infra/ci:v1.1.6@sha256:8d1fcc20e6f1b95ea10427b1ab44439c502f28edca876284e61f6d57ad891d2a

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
