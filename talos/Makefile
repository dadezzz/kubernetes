all: generated/srv-0-nbg-hetz.yaml generated/srv-0-thi-home.yaml

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

# GEN_CONFIG_SRV_0_NBG_HETZ_PATCHES := \
# 	$(GEN_CONFIG_SHARED_PATCHES) \
# 	patches/servers/srv-0-nbg-hetz/base.yaml \
# 	patches/servers/srv-0-nbg-hetz/volumes.yaml \
# 	$(wildcard patches/servers/srv-0-nbg-hetz/networks/*)

# generated/srv-0-nbg-hetz.yaml: secrets.yaml $(GEN_CONFIG_SHARED_CONTROLPLANE_PATCHES) $(GEN_CONFIG_SRV_0_NBG_HETZ_PATCHES)
# 	@talosctl gen config \
# 		$(GEN_CONFIG_SHARED_ARGS) \
# 		--output generated/srv-0-nbg-hetz.yaml \
# 		--output-types controlplane \
# 		$(addprefix --config-patch-control-plane=, $(GEN_CONFIG_SHARED_CONTROLPLANE_PATCHES)) \
# 		$(addprefix --config-patch=, $(GEN_CONFIG_SRV_0_NBG_HETZ_PATCHES))

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
