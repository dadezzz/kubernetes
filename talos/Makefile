all: generated/srv-0-fsk-hetz.yaml generated/srv-0-cor-home.yaml generated/srv-0-thi-home.yaml

gen_config_shared_files = secrets.yaml patches/base.yaml patches/tailscale.yaml patches/controlplane.yaml

gen_config_shared_args = \
	--force \
	--with-docs=false \
	--with-examples=false \
	--with-secrets=secrets.yaml \
	--config-patch=@patches/base.yaml \
	--config-patch=@patches/tailscale.yaml \
	--config-patch-control-plane=@patches/controlplane.yaml \
	k8s.zarantonello.dev \
	https://10.95.0.1:6443

generated/srv-0-fsk-hetz.yaml: $(gen_config_shared_files) patches/servers/srv-0-fsk-hetz/base.yaml patches/servers/srv-0-fsk-hetz/volumes.yaml
	@talosctl gen config \
		$(gen_config_shared_args) \
		--output-types controlplane \
		--output generated/srv-0-fsk-hetz.yaml \
		--config-patch @patches/servers/srv-0-fsk-hetz/base.yaml \
		--config-patch @patches/servers/srv-0-fsk-hetz/volumes.yaml

generated/srv-0-cor-home.yaml: $(gen_config_shared_files) patches/servers/srv-0-cor-home/base.yaml patches/servers/srv-0-cor-home/volumes.yaml
	@talosctl gen config \
		$(gen_config_shared_args) \
		--output-types worker \
		--output generated/srv-0-cor-home.yaml \
		--config-patch @patches/servers/srv-0-cor-home/base.yaml \
		--config-patch @patches/servers/srv-0-cor-home/volumes.yaml

generated/srv-0-thi-home.yaml: $(gen_config_shared_files) patches/servers/srv-0-thi-home/base.yaml patches/servers/srv-0-thi-home/volumes.yaml
	@talosctl gen config \
		$(gen_config_shared_args) \
		--output-types worker \
		--output generated/srv-0-thi-home.yaml \
		--config-patch @patches/servers/srv-0-thi-home/base.yaml \
		--config-patch @patches/servers/srv-0-thi-home/volumes.yaml
