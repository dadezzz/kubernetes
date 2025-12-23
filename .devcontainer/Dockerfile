FROM git.zarantonello.dev/infra/ci:v2.2.0@sha256:198a03613a0e9c4b9bca4f5f369542f8fcee82b570f7552bd1002c57a9f3cefe

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
