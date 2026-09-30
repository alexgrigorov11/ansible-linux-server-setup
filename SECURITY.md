# Security Notes

This project is for Ansible infrastructure automation practice.

## Current safety notes

- The project is currently tested using localhost
- The playbook uses administrator privileges
- No passwords, API tokens, or SSH private keys should be stored in this repository
- The playbook should be reviewed before running on a production server

## Future security improvements

- Create a non-root user with sudo access
- Configure firewall rules
- Harden SSH configuration
- Review file permissions
- Add security checks to CI
