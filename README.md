# Kubernetes

Declarative configuration of the Kubernetes cluster that I use to run services
on my homelab.

The `cluster` directory contains Kubernetes manifests. The cluster is kept in
sync with the repository thanks to `fluxcd`.

The `talos` directory contains the configurations for the nodes that are part of
the cluster.

## Secrets

Secrets are encrypted using [sops](https://getsops.io/), specifically with an
[age](https://github.com/FiloSottile/age) key pair.

The private key should be generated with `age-keygen -o .sops.key` at the root
of the repo. Then copy the **public** key and replace the occurrences in
`.sops.yaml` with the one you just generated.

**Examples**:

```sh
# Encrypt a file
sops -i -e path_to_file

# Decrypt a file
# The variable is only needed outside of the devcontainer or if not using the .sops.key file.
SOPS_AGE_KEY_FILE=/path_to_age_private_key sops -i -d path_to_file
```

To decrypt secrets in the cluster, create a `Secret` that contains the age
private key. The secret has to be generated for each namespace in which a
kustomization that contains secrets is present.

```sh
kubectl create secret generic -n your_namespace --from-file identity.agekey=.sops.key infra-kubernetes-age-key
```
