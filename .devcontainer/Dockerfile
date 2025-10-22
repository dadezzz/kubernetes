FROM git.zarantonello.dev/infra/ci:v1.1.5@sha256:f28b7d8db92e764fbe642064bc98530abc26b748b4bd14999725e3af2e2f5bb3

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
