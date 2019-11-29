# sys-fs/fuse-exfat

### suid
Set the SUID bit on the `mount.exfat-fuse` binary to allow non-privileged users to mount exFAT filesystems.

This flag can be safely disabled, however elevated privileges will be required to mount exFAT. Enabling this flag has additional security implications.
