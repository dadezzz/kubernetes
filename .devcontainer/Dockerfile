FROM git.zarantonello.dev/infra/ci:v2.2.5@sha256:e82d94156b2e56b4d67a92dbd701777cf174f9428a2fa00ba0d13a8d04cb9824

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
