FROM git.zarantonello.dev/infra/ci:v2.3.27@sha256:6eb01e9ad2b817be9f6af98650891537d3e87d1acb696ae3520136a3c4fd7ac5

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
