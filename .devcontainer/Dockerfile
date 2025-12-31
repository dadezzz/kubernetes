FROM git.zarantonello.dev/infra/ci:v2.2.4@sha256:5088231f86965200904f3b595c708d9fbd404a4d959186d5bf6b21fe15e357f1

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
