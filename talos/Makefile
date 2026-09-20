all: generated/srv-hetz-nbg-0.yaml generated/srv-home.yaml

ENCRYPTED_TARGETS := \
	patches/tailscale.yaml \
	secrets.yaml

GEN_CONFIG_SHARED_PATCHES := \
	$(wildcard patches/tailscale.yaml) \
	patches/base.yaml

GEN_CONFIG_SHARED_CONTROLPLANE_PATCHES := \
	patches/controlplane.yaml \

GEN_CONFIG_SHARED_ARGS := \
	--force \
	--with-secrets=secrets.yaml \
	k8s.zarantonello.dev \
	https://[fdb6:fb2a:15d:5f02:a97:98ff:fe83:ae69]:6443

GEN_CONFIG_SRV_HETZ_NBG_0_PATCHES := \
	$(GEN_CONFIG_SHARED_PATCHES) \
	patches/servers/srv-hetz-nbg-0/base.yaml

generated/srv-hetz-nbg-0.yaml: Makefile secrets.yaml $(GEN_CONFIG_SRV_HETZ_NBG_0_PATCHES)
	@talosctl gen config \
		$(GEN_CONFIG_SHARED_ARGS) \
		--output generated/srv-hetz-nbg-0.yaml \
		--output-types worker \
		$(addprefix --config-patch=, $(GEN_CONFIG_SRV_HETZ_NBG_0_PATCHES))

GEN_CONFIG_SRV_HOME_PATCHES := \
	$(GEN_CONFIG_SHARED_PATCHES) \
	patches/servers/srv-home/base.yaml

generated/srv-home.yaml: Makefile secrets.yaml $(GEN_CONFIG_SRV_HOME_PATCHES) $(GEN_CONFIG_SHARED_CONTROLPLANE_PATCHES)
	@talosctl gen config \
		$(GEN_CONFIG_SHARED_ARGS) \
		--output generated/srv-home.yaml \
		--output-types controlplane \
		$(addprefix --config-patch-control-plane=, $(GEN_CONFIG_SHARED_CONTROLPLANE_PATCHES)) \
		$(addprefix --config-patch=, $(GEN_CONFIG_SRV_HOME_PATCHES))

.PHONY: encrypt decrypt

encrypt: $(ENCRYPTED_TARGETS)
	@for i in $(ENCRYPTED_TARGETS) ; do sops -i -e "$$i" ; done

decrypt: $(ENCRYPTED_TARGETS)
	@for i in $(ENCRYPTED_TARGETS) ; do SOPS_AGE_KEY_FILE=../.sops.key sops --ignore-mac -i -d "$$i" ; done
