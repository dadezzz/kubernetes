FROM git.zarantonello.dev/infra/ci:v1.1.20@sha256:ac1db44351f045ca86ba3a1b7563870e125ad277aff7b795cd227000cd37561c

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
