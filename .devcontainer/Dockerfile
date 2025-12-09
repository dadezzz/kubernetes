FROM git.zarantonello.dev/infra/ci:v1.1.31@sha256:1bce306ea67ca15a1d887db7798900914e4240f0e71f0e2b036002d63b5fac09

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
