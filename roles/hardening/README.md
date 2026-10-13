# hardening role

Installs Fail2ban and unattended-upgrades, configures an SSH jail, enables the Fail2ban service, and configures automatic security updates.

Key variables are `fail2ban_maxretry`, `fail2ban_findtime`, and `fail2ban_bantime`.
