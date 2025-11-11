FROM git.zarantonello.dev/infra/ci:v1.1.17@sha256:f6a47aa3851cade029b55fe5e4303dfe8971d57061265b6f357b689109d8af8e

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
