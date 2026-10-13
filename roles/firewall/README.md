# firewall role

Installs and configures UFW with deny-by-default incoming traffic, allow-by-default outgoing traffic, and an explicit SSH allow rule.

Key variables are `firewall_ssh_port`, `firewall_default_incoming`, and `firewall_default_outgoing`.
