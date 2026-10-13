# ssh role

Installs OpenSSH Server and writes a validated hardening drop-in. Defaults disable direct root login, password authentication, keyboard-interactive authentication, and X11 forwarding.

The role validates the SSH configuration before restarting the service.
