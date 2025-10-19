# Ansible Role: Authentication Setup & Hardening

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/authentication-prod/ansible-role-setup)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Galaxy Version](https://img.shields.io/badge/galaxy-authentication--prod.setup-blue.svg)](https://galaxy.ansible.com/ui/standalone/roles/authentication-prod/setup/)

An Ansible role to setup and harden core authentication mechanisms on Debian-based systems (Debian, Ubuntu).

This role automates the process of securing local user authentication by installing necessary PAM modules, enforcing strong password policies, and setting up a basic audit framework.

## Requirements

- Ansible 2.9 or higher.
- Supported target systems:
  - Ubuntu 20.04 (Focal) or later
  - Debian 10 (Buster) or later

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# Whether to install Google Authenticator PAM module for 2FA capabilities
auth_setup_install_google_auth: true

# System user to be created for security and audit purposes
auth_setup_audit_user: "audit-svc"
```

## Dependencies

None.

## Example Playbook

A simple playbook to apply the role to a group of servers:

```yaml
- hosts: servers
  roles:
    - role: authentication-prod.setup
```

To use custom variables:

```yaml
- hosts: servers
  roles:
    - role: authentication-prod.setup
      vars:
        auth_setup_install_google_auth: false
```

## Installation from Ansible Galaxy

You can install this role using the `ansible-galaxy` command:

```bash
ansible-galaxy install authentication-prod.setup
```

## License

MIT

## Author Information

This role was created in 2024 by the team at `ACME Corp` to help standardize security configurations.  
And to present on MEGA Sekurak Hacking Party 2025. :P
