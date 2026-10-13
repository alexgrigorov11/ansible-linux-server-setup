# Ansible Linux Server Setup

An Ansible infrastructure automation project that configures and hardens an Ubuntu Linux server.

The project was created as a practical Platform Engineering / SRE portfolio project and demonstrates reusable Ansible roles, Linux administration, security hardening, Git workflows, and CI validation.

## Features

- Automated package installation
- Non-root administrative user
- SSH public key authentication
- SSH key-only login
- Direct root SSH login disabled
- UFW firewall configuration
- Default deny incoming firewall policy
- SSH firewall rule
- Fail2ban SSH protection
- Automatic security updates
- Reusable Ansible roles
- Idempotent configuration
- GitHub Actions CI

## Project structure

```text
.
├── ansible.cfg
├── inventory/
│   └── hosts
├── playbooks/
│   └── site.yml
├── roles/
│   ├── common/
│   ├── users/
│   ├── firewall/
│   ├── ssh/
│   └── hardening/
├── .github/
│   └── workflows/
│       └── ansible-ci.yml
├── requirements.yml
├── SECURITY.md
├── PROJECT_PLAN.md
├── CHANGELOG.md
└── VERSION

```

## Roles

### common

Installs common Linux administration tools and updates the apt package cache.

### users

Creates a non-root administrative user and configures SSH public key access.

### firewall

Configures UFW with:

- deny incoming by default
- allow outgoing by default
- allow SSH
- enable firewall

### ssh

Applies SSH security settings including:

- disable direct root login
- enable public key authentication
- disable password authentication
- disable keyboard-interactive authentication
- limit authentication attempts
- disable X11 forwarding

### hardening

Adds additional server security:

- Fail2ban
- SSH brute-force protection
- automatic security updates
- unattended upgrades

## Requirements

- Ubuntu Linux
- Ansible
- Python
- sudo privileges

Install required Ansible collections:

```bash
ansible-galaxy collection install -r requirements.yml

```
## Usage

Check the playbook syntax:

```bash
ansible-playbook playbooks/site.yml --syntax-check
```

List all Ansible tasks:

```bash
ansible-playbook playbooks/site.yml --list-tasks
```

Run the complete server configuration:

```bash
sudo ansible-playbook playbooks/site.yml
```

## Verify firewall

Check UFW status:

```bash
sudo ufw status verbose
```

Expected configuration:

```text
Status: active
Default: deny (incoming), allow (outgoing)
22/tcp ALLOW IN
```

## Verify SSH configuration

Check the effective SSH configuration:

```bash
sudo sshd -T | grep -E 'permitrootlogin|pubkeyauthentication|passwordauthentication|kbdinteractiveauthentication|maxauthtries|x11forwarding'
```

Expected result:

```text
permitrootlogin no
pubkeyauthentication yes
passwordauthentication no
kbdinteractiveauthentication no
maxauthtries 3
x11forwarding no
```

## Verify Fail2ban

Check SSH protection:

```bash
sudo fail2ban-client status sshd
```

## Idempotency

The playbook is designed to be idempotent.

Running it multiple times should not create unnecessary changes:

```bash
sudo ansible-playbook playbooks/site.yml
```

Expected final result:

```text
changed=0
failed=0
```

## CI

GitHub Actions automatically validates the project on pushes and Pull Requests targeting `main`.

The CI workflow:

- installs Ansible
- installs required Ansible collections
- checks playbook syntax
- verifies that all tasks and roles can be loaded

Workflow file:

```text
.github/workflows/ansible-ci.yml
```

## Security

The project includes:

- non-root administration
- SSH key-only authentication
- disabled direct root SSH login
- disabled SSH password authentication
- UFW firewall
- Fail2ban SSH protection
- automatic security updates

See `SECURITY.md` for additional security information.

## Current scope

Version 1.0.0 configures and hardens an Ubuntu Linux host locally.

A future version can extend the project to configure remote Linux servers over SSH.

## Version

v1.0.0
