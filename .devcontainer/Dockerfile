FROM git.zarantonello.dev/infra/ci:v1.1.33@sha256:47aed7138b51aaae8f5cd33f71930e7ac4c6f177644ab3854b8707572bccc75f

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
