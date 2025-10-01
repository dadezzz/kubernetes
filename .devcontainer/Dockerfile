FROM git.zarantonello.dev/infra/ci:v2.0.0@sha256:19530505e0ed05a7201c9050509ce136bdc0604de9154f2b4d560166833aa6f1

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.0@sha256:cfc60e314f1e756eda73e22520c96ac3e513d31ac6e948be956ab7ee934795fe /usr/local/bin/flux /usr/local/bin/
