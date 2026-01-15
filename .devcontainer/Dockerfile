FROM git.zarantonello.dev/infra/ci:v2.3.6@sha256:9090c7139d93376cc98fb38ba38767ebf6d8efdbd802e7ed06d9c12b1f6ca496

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
