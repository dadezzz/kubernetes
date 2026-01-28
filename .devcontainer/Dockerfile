FROM git.zarantonello.dev/infra/ci:v2.3.19@sha256:53bbf41be7ae9f775203d3779465bbe8f31bb149985e9ad9253f526e5a9c124e

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
