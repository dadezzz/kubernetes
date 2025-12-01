FROM git.zarantonello.dev/infra/ci:v1.1.26@sha256:a909d6507cd5dcd7567596a379c91ff73a514002a499941f433762ce463174cb

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
