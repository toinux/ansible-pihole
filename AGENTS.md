# Project guidance

- This playbook manages two live Pi-hole DNS servers with keepalived failover. `site.yaml` applies roles serially; preserve availability when changing deployment order.
- `inventory.yaml` is ignored and contains private host information and credentials. Never commit it or print secrets in logs, diffs, or PRs.
- Use the versions in `mise.toml`. Run `mise exec -- ansible-playbook -i inventory.yaml --syntax-check site.yaml` and a check-mode run before an authorized deployment. Check mode cannot guarantee container or service changes are safe.
- `roles/pihole` renders the Docker Compose stack and DNSCrypt config; Nebula Sync runs on the priority-100 host. Verify both nodes and DNS after changes.
- The setup role upgrades packages and can reboot servers; review its effects before running the full playbook against live hosts.
