FROM git.zarantonello.dev/infra/ci/pnpm:latest@sha256:81b5a141b314b6a79449dd56a9fbf6ee7dc59fbe72a7c75a9fcac29f3bdc7e7c

# Add standard packages for devcontainer

RUN apk add --no-cache git gpg

ENV PNPM_HOME="/usr/local/share/pnpm"
ENV PATH="/usr/local/share/pnpm:$PATH"

# Install linting tools.

# # renovate: datasource=npm depName=@biomejs/biome versioning=npm
ENV BIOME_VERSION="2.2.3"
RUN pnpm install -g "@biomejs/biome@$BIOME_VERSION"

# # renovate: datasource=npm depName=prettier versioning=npm
ENV PRETTIER_VERSION="3.6.2"
RUN pnpm install -g "prettier@$PRETTIER_VERSION"

RUN apk add --no-cache yamllint

# Install tools to manage k8s.

RUN apk add --no-cache kubectl sops age helm kustomize
COPY --from=docker.io/fluxcd/flux-cli:v2.6.4@sha256:d6734ea180b0f5135e6a343482da1a669c526ef85525da53a6415c6a9f359861 /usr/local/bin/flux /usr/local/bin/

USER 0:0
ENTRYPOINT []
HEALTHCHECK NONE
