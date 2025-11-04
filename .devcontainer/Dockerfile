FROM git.zarantonello.dev/infra/ci:v1.1.11@sha256:cd93ca425527d9d0e93f4f94b4ba4b942dd42a9ae806bbf915e78d70dea3191c

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.3@sha256:334f73637220fe587fcc8439f35a841c92c44d4695895fd04c77731bd418f14e /usr/local/bin/flux /usr/local/bin/
