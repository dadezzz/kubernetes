FROM git.zarantonello.dev/infra/ci:v2.3.18@sha256:de6c314de0cda8e72732bf873728ced2211dcfe02e3980aae4c826f59a06d412

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
