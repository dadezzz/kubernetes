FROM git.zarantonello.dev/infra/ci:v1.1.9@sha256:8d13f82f8ff99b206c2a33eee0a4bb37affdf5a55743c819b9ed75be929233d7

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
