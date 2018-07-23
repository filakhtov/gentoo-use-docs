# sys-auth/pam_mktemp

### prevent-removal
Pass the `USE_APPEND_FL=1` (`0` if disabled) variable to the `make` command. Set an append-only flag on the main private temporary directory to prevent its removal to avoid situations where a malicious user can create a directory with the same name and have a control of private space.

It is recommended to enable this flag. However, it does not make sense if a temporary space is stored on a filesystem without apppend-only flag support.

### selinux
Pass the `USE_SELINUX=1` (`0` when disabled) variable to the `make` command. Make sure that temporary private directories are created with an appropriate context when running under the SELinux-restricted kernel.

This flag should only be ever toggled system-wide, i.e. as part of the SELinux-enabled Portage profile.
