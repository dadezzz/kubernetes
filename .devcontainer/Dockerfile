FROM git.zarantonello.dev/infra/ci:v2.3.17@sha256:0b6ef7ca3963309b5349a683dd24b910cc6a636777b58b305585be9b86c76f3c

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
