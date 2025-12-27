FROM git.zarantonello.dev/infra/ci:v2.2.2@sha256:a3fe21ce07321802ac4e8e2ac25f68c8df09874f89a55b2e63ffb9519da737e4

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
