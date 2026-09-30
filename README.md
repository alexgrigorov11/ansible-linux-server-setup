# Ansible Linux Server Setup Automation

An Ansible project that automates basic Linux server setup for infrastructure automation practice.

## What this project does

- Updates apt package cache
- Installs common Linux tools
- Uses a structured Ansible project layout
- Runs against localhost for safe testing
- Demonstrates idempotent Ansible automation

## Installed tools

- curl
- git
- vim
- htop
- tree
- unzip

## Project structure

```text
ansible-linux-server-setup/
├── inventory/
│   └── hosts
├── playbooks/
│   └── site.yml
├── README.md
└── .gitignore
