FROM git.zarantonello.dev/infra/ci:v1.1.23@sha256:167af5044e7365a3eb7f6964afc37979855ed4cd6df893d66781a941e07be423

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
