FROM git.zarantonello.dev/infra/ci:v1.1.23@sha256:167af5044e7365a3eb7f6964afc37979855ed4cd6df893d66781a941e07be423

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
