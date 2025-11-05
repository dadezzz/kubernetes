FROM git.zarantonello.dev/infra/ci:v1.1.12@sha256:4c6103c2bc523eebf514c710b4ce3f52ff392ac903a4beab4ccb8512becfd19b

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
