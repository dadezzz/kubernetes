FROM git.zarantonello.dev/infra/ci:v2.2.7@sha256:d53c5a95c59bc4d866dad2beeb6f7c5577eef04db60ee83899a9adce03f482ad

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
