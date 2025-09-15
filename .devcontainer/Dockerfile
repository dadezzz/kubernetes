FROM git.zarantonello.dev/infra/ci:v1.0.4@sha256:3ba3e6042124260aab1a09e4d709e56f9990c778b1fe90015ab13cabe37e917f

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.6.4@sha256:d6734ea180b0f5135e6a343482da1a669c526ef85525da53a6415c6a9f359861 /usr/local/bin/flux /usr/local/bin/
