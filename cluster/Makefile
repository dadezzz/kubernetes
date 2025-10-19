.PHONY: encrypt decrypt

ENCRYPTED_TARGETS = \
	./cert-manager/secrets/acme-cloudflare-dns-api-token.yaml \
	./forgejo-runner/_generated/secrets/forgejo-runner.env \
	./forgejo/_generated/secrets/forgejo.env \
	./grafana/_generated/secrets/grafana.env \
	./immich/_generated/secrets/immich.env \
	./immich/_generated/secrets/postgres.env \
	./vaultwarden/_generated/secrets/vaultwarden.env

encrypt: $(ENCRYPTED_TARGETS)
	@for i in $(ENCRYPTED_TARGETS) ; do sops -i -e "$$i" ; done

decrypt: $(ENCRYPTED_TARGETS)
	@for i in $(ENCRYPTED_TARGETS) ; do SOPS_AGE_KEY_FILE=../.sops.key sops -i -d "$$i" ; done
