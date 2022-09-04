# Features

- 2 [docker Pi-Hole](https://github.com/pi-hole/docker-pi-hole) instances
- [dnscryp-proxy](https://dnscrypt.info), [with docker](https://registry.hub.docker.com/r/klutchell/dnscrypt-proxy)
- failover with keepalived
- firewalld
- replication with [gravity-sync](https://github.com/vmstan/gravity-sync/) (to finish) 

# Requirements
## Servers

2 Debian 11 servers/VMs. Could work with debian 10.
Ubuntu would need adaptation with systemd-resolved

## Ansible

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

```shell
python3 -m pip install --user ansible
```
or
```shell
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible
```

Then install required modules :

```shell
ansible-galaxy install -r requirements.yaml
```

# Installation

Copy `inventory.yaml.sample` to `inventory.yaml` and adjust settings
```shell
ansible-playbook -i inventory.yaml -D site.yaml
```

# TODO

## Gravity-sync

Add first initialization and cron