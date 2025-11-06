FROM git.zarantonello.dev/infra/ci:v1.1.14@sha256:3d825d038ea6cbef0d50f75917953f47729b4ab08666c40cc7d89ceef6a89f7e

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
