FROM git.zarantonello.dev/infra/ci:v1.0.6@sha256:31e11c2e307e110dcf8063a5820b6d456d7a2247dedf2031442788ccc7ec3ae0

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.0@sha256:cfc60e314f1e756eda73e22520c96ac3e513d31ac6e948be956ab7ee934795fe /usr/local/bin/flux /usr/local/bin/
