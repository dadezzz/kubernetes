FROM git.zarantonello.dev/infra/ci:v1.1.37@sha256:8134ca5b4097214e1c6b7e9786e8fb171cd1e6a97a00360183c8275eb6a5fcbd

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
