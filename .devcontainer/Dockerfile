FROM git.zarantonello.dev/infra/ci:v1.1.24@sha256:83cf1b380d6092c0eb99d156c780b8a0a2aba04e6992922c4574c6457ff62e2a

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
