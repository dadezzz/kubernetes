FROM git.zarantonello.dev/infra/ci:v2.3.9@sha256:2203dbfcd904b213bb61f3ca88986c04f6e3bbe969969b7d077a7e16eeda678e

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
