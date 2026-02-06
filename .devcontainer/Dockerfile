FROM git.zarantonello.dev/infra/ci:v2.3.21@sha256:acc6484b0da3e3f18878873dfb65e3323334af1ca131ce9b60ab1b7422fbc893

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
