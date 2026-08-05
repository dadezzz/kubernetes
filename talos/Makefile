all: generated/srv-hetz-nbg-0.yaml generated/srv-home.yaml

ENCRYPTED_TARGETS := \
	./patches/network/tailscale.yaml \
	./secrets.yaml

GEN_CONFIG_SHARED_PATCHES := \
	patches/base.yaml \
	$(wildcard patches/network/*)

GEN_CONFIG_SHARED_CONTROLPLANE_PATCHES := \
	patches/controlplane.yaml \

GEN_CONFIG_SHARED_ARGS := \
	--force \
	--with-docs=false \
	--with-examples=false \
	--with-secrets=secrets.yaml \
	k8s.zarantonello.dev \
	https://100.107.181.54:6443

GEN_CONFIG_SRV_HETZ_NBG_0_PATCHES := \
	$(GEN_CONFIG_SHARED_PATCHES) \
	patches/servers/srv-hetz-nbg-0/base.yaml \
	patches/servers/srv-hetz-nbg-0/volumes.yaml \
	$(wildcard patches/servers/srv-hetz-nbg-0/networks/*)

generated/srv-hetz-nbg-0.yaml: secrets.yaml $(GEN_CONFIG_SHARED_CONTROLPLANE_PATCHES) $(GEN_CONFIG_SRV_HETZ_NBG_0_PATCHES)
	@talosctl gen config \
		$(GEN_CONFIG_SHARED_ARGS) \
		--output generated/srv-hetz-nbg-0.yaml \
		--output-types worker \
		$(addprefix --config-patch=, $(GEN_CONFIG_SRV_HETZ_NBG_0_PATCHES))

GEN_CONFIG_SRV_HOME_PATCHES := \
	$(GEN_CONFIG_SHARED_PATCHES) \
	patches/servers/srv-home/base.yaml \
	patches/servers/srv-home/volumes.yaml \
	$(wildcard patches/servers/srv-home/networks/*)

generated/srv-home.yaml: secrets.yaml $(GEN_CONFIG_SRV_HOME_PATCHES)
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
