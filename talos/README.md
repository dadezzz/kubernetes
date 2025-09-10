# Talos

My nodes run Talos Linux, a config driven minimal linux distribution, created
for the specific purpose of running kubernetes.

I try to standardize the configuration as much as possible, but due to the
servers being in different physical locations with different environment, some
individual adjustments need to be made.

To create your own cluster:

1. Navigate to the `talos` directory.
2. Generate a different set of secrets with `talosctl gen secrets`. This will
   overwrite the `secrets.yaml` file
3. Set your own Tailscale auth key in `patches/tailscale.yaml`
4. Create directories `patches/servers/your_server_hostname/` using the same
   format as the existing ones.
5. Update the files inside the server specific directory.
6. Update hostnames in `Makefile` to build for your own servers.

Running `make` should output for each server a file in
`generated/your_server_hostname.yaml`.

## Node naming convention

```
 -- srv prefix
 |
 |     -- 3 letter code for location
 |     |
srv-0-cor-home
    |       |
    |       -- 4 letter code for cloud provider (home is for non cloud provider servers)
    |
    -- server ID. If in the same zone, different ID
```

## Inter node network

Nodes communicate between themselves through a Wireguard network, specifically
on the `10.95.0.0/24` subnet and a corresponding IPv6 one.

Tailscale is used to access the cluster from client devices, both for management
and for connecting to private services exposed via `LoadBalancer`.

The default CNI is disabled. Instead I use Cilium in `eBPF Datapath` mode. It
provides increased observability for network flows and a better support of
network policies if I decide to implement them in the future.
