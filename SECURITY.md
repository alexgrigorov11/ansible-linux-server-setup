# Security Notes

This project is for Ansible infrastructure automation practice.

## Current safety notes

- The project is currently tested using localhost
- The playbook uses administrator privileges
- No passwords, API tokens, or SSH private keys should be stored in this repository
- The playbook should be reviewed before running on a production server
- The current inventory targets localhost; remote SSH provisioning is not yet implemented
- SSH access must be verified with a working public key before disabling password login

## Implemented controls

- A non-root administrative user is created
- UFW is configured with deny-by-default incoming traffic
- SSH is hardened with key-only authentication and no direct root login
- Fail2ban protects the SSH service
- Unattended security updates are configured

## Future improvements

- Add an integration test against a disposable Ubuntu VM
- Add secret scanning and dependency scanning to CI
- Parameterize SSH keys and remote inventory for safe multi-host use
