FROM git.zarantonello.dev/infra/ci:v1.1.4@sha256:142f9346ffd3379266ef1d24727caafaceaae94ac65fe9f4a2d729200cce1eac

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.2@sha256:c10e77794dc4519322cbc58e75c7f612125e4276b726c6cb019d87e9dadb08dd /usr/local/bin/flux /usr/local/bin/
