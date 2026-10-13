# Project Plan

## Project name

Ansible Linux Server Setup Automation

## Goal

Build an Ansible project that automates basic Linux server setup.

## Current features

- Local Ansible inventory
- Basic playbook
- Apt package cache update
- Common tool installation
- Idempotent execution
- Reusable roles for users, firewall, SSH, and hardening
- GitHub Actions syntax and lint validation

## Next improvements

- Test on a real Linux VM
- Add Molecule or integration tests
- Pin collection versions for reproducible builds
- Add remote inventory and safe SSH-key variables

## Definition of done

The project is complete when it can configure a clean Linux server with common tools, users, security settings, firewall configuration, and documentation.
