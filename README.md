Role Name
=========

hostname

[![Build Status](https://travis-ci.org/cmihai-ansible/hostname.svg?branch=master)](https://travis-ci.org/cmihai-ansible/hostname)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devopstoolbox.hostname](https://galaxy.ansible.com/devopstoolbox.hostname)

```bash
ansible-galaxy install devopstoolbox.hostname
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```yaml
hostname_remove_packages: true
hostname_enable_service: true
hostname_enable_selinux: true
hostname_firewall_configure: true
hostname_firewall_rules:
  - service:
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install hostname on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: hostname is configured
      import_role:
        name: devopstoolbox.hostname
      vars:
        hostname_remove_packages: true
        hostname_enable_service: true
        hostname_firewall_configure: true
        hostname_firewall_rules:
          - service:
      tags: hostname
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/devopstoolbox.)
