FROM git.zarantonello.dev/infra/ci:v1.1.18@sha256:1193c505449ba7f463b186982d48fb4593e275635677288998b43b1736390f95

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
