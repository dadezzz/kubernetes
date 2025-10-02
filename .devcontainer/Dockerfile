FROM git.zarantonello.dev/infra/ci:v1.0.5

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.0@sha256:cfc60e314f1e756eda73e22520c96ac3e513d31ac6e948be956ab7ee934795fe /usr/local/bin/flux /usr/local/bin/
