FROM git.zarantonello.dev/infra/ci:v1.1.35@sha256:3a624c7fd03ca2b271cb7b1c19762d88cac270b5e92338ec5b00259fd5011dd3

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
