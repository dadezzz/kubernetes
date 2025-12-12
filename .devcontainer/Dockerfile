FROM git.zarantonello.dev/infra/ci:v1.1.32@sha256:14672c10ceefe7490bc350e8a1080514c15146e0635fbe818b1e5252c3d5a37b

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
