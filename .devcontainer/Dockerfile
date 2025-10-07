FROM git.zarantonello.dev/infra/ci:v1.0.6@sha256:31e11c2e307e110dcf8063a5820b6d456d7a2247dedf2031442788ccc7ec3ae0

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.1@sha256:307a90e7891fca7ba23030f366b7bcc2f27f353502c826f10596bd1dd5ea4f53 /usr/local/bin/flux /usr/local/bin/
