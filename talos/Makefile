all: generated/srv-0-nbg-hetz.yaml generated/srv-0-cor-home.yaml generated/srv-0-thi-home.yaml

ENCRYPTED_TARGETS = \
	./patches/base.yaml \
	./patches/servers/srv-0-cor-home/base.yaml \
	./patches/servers/srv-0-nbg-hetz/base.yaml \
	./patches/servers/srv-0-thi-home/base.yaml \
	./patches/tailscale.yaml \
	./secrets.yaml

GEN_CONFIG_SHARED_FILES = \
	secrets.yaml \
	patches/base.yaml \
	patches/tailscale.yaml \
	patches/controlplane.yaml

GEN_CONFIG_SHARED_ARGS = \
	--force \
	--with-docs=false \
	--with-examples=false \
	--with-secrets=secrets.yaml \
	--config-patch=@patches/base.yaml \
	--config-patch=@patches/tailscale.yaml \
	--config-patch-control-plane=@patches/controlplane.yaml \
	k8s.zarantonello.dev \
	https://10.95.0.1:6443

generated/srv-0-nbg-hetz.yaml: $(GEN_CONFIG_SHARED_FILES) patches/servers/srv-0-nbg-hetz/base.yaml patches/servers/srv-0-nbg-hetz/volumes.yaml
	@talosctl gen config \
		$(GEN_CONFIG_SHARED_ARGS) \
		--output-types controlplane \
		--output generated/srv-0-nbg-hetz.yaml \
		--config-patch @patches/servers/srv-0-nbg-hetz/base.yaml \
		--config-patch @patches/servers/srv-0-nbg-hetz/volumes.yaml

generated/srv-0-cor-home.yaml: $(GEN_CONFIG_SHARED_FILES) patches/servers/srv-0-cor-home/base.yaml patches/servers/srv-0-cor-home/volumes.yaml
	@talosctl gen config \
		$(GEN_CONFIG_SHARED_ARGS) \
		--output-types worker \
		--output generated/srv-0-cor-home.yaml \
		--config-patch @patches/servers/srv-0-cor-home/base.yaml \
		--config-patch @patches/servers/srv-0-cor-home/volumes.yaml

generated/srv-0-thi-home.yaml: $(GEN_CONFIG_SHARED_FILES) patches/servers/srv-0-thi-home/base.yaml patches/servers/srv-0-thi-home/volumes.yaml
	@talosctl gen config \
		$(GEN_CONFIG_SHARED_ARGS) \
		--output-types worker \
		--output generated/srv-0-thi-home.yaml \
		--config-patch @patches/servers/srv-0-thi-home/base.yaml \
		--config-patch @patches/servers/srv-0-thi-home/volumes.yaml

.PHONY: encrypt decrypt

encrypt: $(ENCRYPTED_TARGETS)
	@for i in $(ENCRYPTED_TARGETS) ; do sops -i -e "$$i" ; done

decrypt: $(ENCRYPTED_TARGETS)
	@for i in $(ENCRYPTED_TARGETS) ; do SOPS_AGE_KEY_FILE=../.sops.key sops -i -d "$$i" ; done
