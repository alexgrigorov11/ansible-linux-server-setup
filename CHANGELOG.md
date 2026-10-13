# Changelog

## v1.0.0

First portfolio-ready release of the Ansible Linux Server Setup project.

### Added

- Structured Ansible project architecture
- Reusable `common` role
- Reusable `users` role
- Non-root administrative user
- SSH public key deployment
- SSH key-only authentication
- Reusable `firewall` role
- UFW firewall automation
- Reusable `ssh` role
- SSH hardening configuration
- Reusable `hardening` role
- Fail2ban SSH protection
- Automatic security updates
- Ansible collection requirements
- GitHub Actions CI
- Project documentation
- Security documentation

### Security

- Disabled direct root SSH login
- Disabled SSH password authentication
- Disabled keyboard-interactive authentication
- Enabled public key authentication
- Limited SSH authentication attempts
- Disabled X11 forwarding
- Enabled default-deny incoming firewall policy
- Allowed SSH explicitly through UFW
- Added Fail2ban protection for SSH
- Enabled automatic security updates

### Validation

The project was tested for:

- Ansible syntax validation
- Complete task loading
- SSH key authentication
- Password-only SSH rejection
- UFW configuration
- Fail2ban SSH protection
- Idempotency

### Status

This is the first portfolio-ready release of the project.
