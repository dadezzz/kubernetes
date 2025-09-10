# Default namespace

  <!-- # Create a secret that contains age's private key: -->
  <!-- # -->
  <!-- # kubectl create secret generic \ -->
  <!-- #   --namespace default \ -->
  <!-- #   --from-literal identity.agekey=yourkey \ -->
  <!-- #   forgejo-iac-manifests-age-key -->

Here we override the pod admission policy to allow testing things with
`kubectl run`.

This namespace also contains the fluxcd resources needed to keep the cluster in
sync with the git repository.
