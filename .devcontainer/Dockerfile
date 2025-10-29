FROM git.zarantonello.dev/infra/ci:v1.1.10@sha256:1baa61e11ad3bdb27531db197197a1517d4edccf499d55c08c8b38f327f5daea

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
