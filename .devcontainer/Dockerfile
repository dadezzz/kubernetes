FROM git.zarantonello.dev/infra/ci:v2.3.16@sha256:4c39477491694b815f2f61dee8a8f09580f4208cee1fe7747d4043790830817b

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
