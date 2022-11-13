# Ansible role for Redis exporter

This role will setup [Node exporter](https://github.com/oliver006/redis_exporter) on any Linux machine using systemd.

## Role Variables

- `redis_exporter_version`: the version of Redis exporter that will be installed.

The role will download the Redis exporter release on the deployer and upload the binary to the target host.

If the `/usr/local/bin/redis_exporter` binary already exists, the role will skip the install steps. You can force them (to update, for instance), by setting `redis_exporter_force_install` to true.

- `redis_exporter_system_group`: the name of the group that will run Node exporter.(`node-exporter`)
- `redis_exporter_system_user`: the name of the user that will run Node exporter. Default to `redis_exporter_system_group`.
- `redis_exporter_web_listen_address`: the address Node exporter will listen on. (`0.0.0.0:9121`)

## Example playbook

```yaml
---
- hosts: myhost
  roles: redis-exporter
```

## License

MIT. See LICENSE for more details.

## Author Information

See my other Ansible roles at [angristan/ansible-roles](https://github.com/angristan/ansible-roles).
