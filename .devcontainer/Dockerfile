FROM git.zarantonello.dev/infra/ci:v2.2.1@sha256:95b4b3ef4763618c1999c4486a3aa8ee2f30622d4830576f0dadb6fffb535ce8

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
