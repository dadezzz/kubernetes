FROM git.zarantonello.dev/infra/ci:v2.3.13@sha256:fcfe32ca7fd661a0d0de41b2b3f5be84cfc0f3ebfc2480d2caf7b0e361bf98e1

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
