FROM git.zarantonello.dev/infra/ci:v1.0.8@sha256:b67f727662fc1f896e564b8f43e1c06465a298fbe0510945fa7348a56d3b9ffc

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.1@sha256:307a90e7891fca7ba23030f366b7bcc2f27f353502c826f10596bd1dd5ea4f53 /usr/local/bin/flux /usr/local/bin/
