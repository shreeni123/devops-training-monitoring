# DigitalOcean Rancher Quickstart

Two single-node RKE Kubernetes clusters will be created from two droplets running Ubuntu 20.04 and Docker.
Both instances will be accessible over SSH using the SSH keys `id_rsa` and `id_rsa.pub`.

## Variables

###### `do_token`
- **Required**
DigitalOcean API token used to create infrastructure

###### `do_region`
- Default: **`"nyc1"`**
DigitalOcean region used for all resources

###### `prefix`
- Default: **`"quickstart"`**
Prefix added to names of all resources

###### `droplet_size`
- Default: **`"s-2vcpu-4gb"`**
Droplet size used for all droplets

###### `docker_version`
- Default: **`"19.03"`**
Docker version to install on nodes

###### `rancher_kubernetes_version`
- Default: **`"v1.21.4+k3s1"`**
Kubernetes version to use for Rancher server cluster

See `rancher-common` module variable `rancher_kubernetes_version` for more details.

###### `workload_kubernetes_version`
- Default: **`"v1.20.12-rancher1-1"`**
Kubernetes version to use for managed workload cluster

See `rancher-common` module variable `workload_kubernetes_version` for more details.

###### `cert_manager_version`
- Default: **`"1.5.3"`**
Version of cert-manager to install alongside Rancher (format: 0.0.0)

See `rancher-common` module variable `cert_manager_version` for more details.

###### `rancher_version`
- Default: **`"v2.6.0"`**
Rancher server version (format v0.0.0)

See `rancher-common` module variable `rancher_version` for more details.

###### `rancher_server_admin_password`
- **Required**
Admin password to use for Rancher server bootstrap

See `rancher-common` module variable `admin_password` for more details.

