FROM git.zarantonello.dev/infra/ci:v1.1.15@sha256:7ea4e979773e70f6b8271370d19a28acdc23c7eda80cddea805fc7d295bd7ba8

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
