FROM git.zarantonello.dev/infra/ci:v1.1.25@sha256:a9c92719ff92c602271cf7681086ddc155f31d9f5639b9746f793775fef0273e

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
