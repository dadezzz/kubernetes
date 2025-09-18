FROM git.zarantonello.dev/infra/ci:v2.0.0@sha256:19530505e0ed05a7201c9050509ce136bdc0604de9154f2b4d560166833aa6f1

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.6.4@sha256:d6734ea180b0f5135e6a343482da1a669c526ef85525da53a6415c6a9f359861 /usr/local/bin/flux /usr/local/bin/
