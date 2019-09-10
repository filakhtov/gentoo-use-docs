# net-fs/cifs-utils

### acl
Pass a `--enable-cifsacl=cifsidmap` option to a configure script. Build and install a `cifs.idmap` userspace helper for mapping ids for CIFS (Common Internet File System) - a callout program that does a number of activities that the kernel cannot easily do itself when handling mounts with the `cifsaclmount` option.

This flag should only be enabled if there is a need to handle UID/GID mappings.

### ads
Pass a `--enable-cifsupcall` option to a configure script. Build and install a `cifs.upcall` userspace upcall helper for CIFS (Common Internet File System) that is generally intended to be run when the kernel calls `request-key` for a particular key type.

This flag should only be enabled if there is a need to authenticate using a Kerberos 5 protocol.

### caps
Pass a `--with-libcap` option to a configure script. Use a `libcap` library to drop root privileges and retrain only minimal necessary set of POSIX capabilities that are required for proper operation.

It is recommended to enable this flag to improve security.

### creds
Pass a `--enable-cifscreds` option to a configure script. Build and install a `cifscreds` binary to manage NTLM credentials (username and password) in kernel keyring for the purpose of establishing sessions in multiuser mounts.

This flag should be enabled if there is a need for the `cifcreds` tool.

### pam
Pass a `--enable-pam` option to a configure script. Build and install a `pam_cifscreds` PAM module to automatically add credentials (username and password) to kernel keyring at login for mounts with the `multiuser` that don't use krb5 authentication.

This flag should be enabled if there is a need to use `multiuser` CIFS mounts without a Kerberos authentication.
