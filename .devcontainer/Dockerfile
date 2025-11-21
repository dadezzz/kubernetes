FROM git.zarantonello.dev/infra/ci:v1.1.22@sha256:e885d4074a5876dbbb6de65cfcc185655ec4143e4915a6096893bd5aa04da3b7

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
