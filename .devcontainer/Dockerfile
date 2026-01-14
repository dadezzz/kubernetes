FROM git.zarantonello.dev/infra/ci:v2.3.4@sha256:b55032fdabba9915aff31ed4295bfb614afddb0ec0f6af2daa5ffa6473e15ba2

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
