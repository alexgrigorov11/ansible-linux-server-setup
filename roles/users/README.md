# users role

Creates the configured non-root administrative user, adds it to the `sudo` group, and installs the controller's public SSH key.

Key variables are `admin_user` and `ssh_public_key_path`. Verify key-based access before applying SSH hardening.
