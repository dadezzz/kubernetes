FROM git.zarantonello.dev/infra/ci:v1.1.30@sha256:01b06fc723f42e0175c7ae54bb35406941220c4ae08ec22e7c9274d3b5a037df

RUN apt update && \
    apt install -y --no-install-recommends kubectl kustomize && \
    rm -rf /var/lib/apt/lists/*

COPY --from=docker.io/fluxcd/flux-cli:v2.7.5@sha256:3a4f9b0a26c26db8193c476e0abe33c32187eae8ce7a0a604d38a51783544946 /usr/local/bin/flux /usr/local/bin/
