# Role Name

Install and configure firewalld

## Requirements

None as the firewalld package is being installed.

## Role Variables

Default variables are set in `defaults/main.yml`.

## Dependencies

No dependency on other Ansible Galaxy roles.

## Example Playbook

```yaml
---
- hosts: servers
  vars:
    firewalld_services_enable:
      - https
      - ssh
    firewalld_services_disable:
      - ftp
      - http
    firewalld_rich_rule_add:
      - zone: public
        family: ipv4
        address: 192.0.2.0/24
        port: 22
        protocol: tcp
        action: accept
  roles:
      - { role: hspaans.firewalld, become: true }
```

## License

MIT

## Author Information

This role was created in 2020 by [Hans Spaans](https://github.com/hspaans).
