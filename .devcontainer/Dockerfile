FROM git.zarantonello.dev/infra/ci:v1.1.16@sha256:d84c3d560d24d3aed63a85c93fc677ef5592cf218fe36346ce3e4813785f8a38

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
