FROM git.zarantonello.dev/infra/ci:v1.1.21@sha256:d9164925e34d0d9b3034002400a36813c422881a800a80593cd1cdb1d88495f0

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
