FROM git.zarantonello.dev/infra/ci:v1.0.7@sha256:a4fa504ee727b8756cd4d192978c87e439c59a326212985fd868edcfce087801

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.1@sha256:307a90e7891fca7ba23030f366b7bcc2f27f353502c826f10596bd1dd5ea4f53 /usr/local/bin/flux /usr/local/bin/
