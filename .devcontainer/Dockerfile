FROM git.zarantonello.dev/infra/ci:v2.3.22@sha256:8ece2e31a94773f1acdde8953e34efd346faa29e18e59e2f4dccbd1ba360eab3

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
