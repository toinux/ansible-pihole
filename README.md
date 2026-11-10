# Features

- 2 [docker Pi-Hole](https://github.com/pi-hole/docker-pi-hole) instances
- [dnscryp-proxy](https://dnscrypt.info), [with docker](https://registry.hub.docker.com/r/klutchell/dnscrypt-proxy)
- failover with keepalived
- firewalld

# Requirements
## Servers

2 Debian 11 servers/VMs. Could work with debian 10.
Ubuntu would need adaptation with systemd-resolved

## Ansible

Install the versions in `mise.toml` with [mise](https://mise.jdx.dev/):

```shell
mise trust
mise install
```

The Ansible package includes the collections listed in `requirements.yaml`.
The setup role installs the Docker Compose v2 plugin on the servers.

# Installation

Copy `inventory.yaml.sample` to `inventory.yaml` and adjust settings
```shell
ansible-playbook -i inventory.yaml -D site.yaml
```
