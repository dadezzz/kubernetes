FROM git.zarantonello.dev/infra/ci:v2.3.25@sha256:0557ae2dadaf2220a85582fbff13b11cc229e49766934a733c4144505d07c6f9

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
