FROM git.zarantonello.dev/infra/ci:v1.1.28@sha256:686364bb3537347897d5f3aa7a505de68013d95668ad53b25b6a1b96750f79bb

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
