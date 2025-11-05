FROM git.zarantonello.dev/infra/ci:v1.1.13@sha256:a26f16fb8ff9b0eab9d4c712b4935308bb7edee6e82f6236c4796d0a506f0e05

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
