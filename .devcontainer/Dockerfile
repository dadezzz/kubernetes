FROM git.zarantonello.dev/infra/ci:v2.2.8@sha256:4aed5948687bb24c6700a66be4df3a3895c9b8ce4209d3a0d233e024782cd8e3

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
