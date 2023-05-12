# net-misc/openssh

### audit
Pass the `--with-audit=linux` option to the configure script. Provide an ability to report various SSH events through a Kernel Audit Subsystem.

It is safe to disable the flag. This flag is useful for environments where security auditing is necessary.

### debug
Append the `-DSANDBOX_SECCOMP_FILTER_DEBUG` option to a `CPPFLAGS` variable. Changes seccomp denial method from a default `SECCOMP_RET_KILL` to a `SECCOMP_RET_TRAP` that provides additional information about the failed syscall.

This flag is only useful for debugging a seccomp filter functionality and should normally be disabled.

### kerberos
Pass the `--with-kerberos5=/usr` option to the configure script. Provide support for authentication using a Kerberos protocol.

Enable a `KerberosAuthentication`, a `KerberosOrLocalPasswd`, a `KerberosTicketCleanup` and a `KerberosGetAFSToken` options support for an SSH daemon.

This flag is safe to disable.

### ldap
Patch an OpenSSH source to provide a LDAP authentication support (aka OpenSSH-LPK, LDAP Public Key). Pass the `--with-ldap` option to the configure script. Provide an ability to store public keys in LDAP and allow grouping of machines in LDAP data to limit a user access to specific machines.

Enable a `UseLPK`, a `LpkServers`, a `LpkUserDN`, a `LpkGroupDN`, a `LpkBindDN`, a `LpkBindPw`, a `LpkServerGroup`, a `LpkForceTLS`, a `LpkSearchTimelimit`, a `LpkLdapConf`, a `LpkFilter` and a `LpkBindTimelimit` options for SSH daemon.

It is safe to disable the flag.

### ldns
Pass the `--with-ldns` option to the configure script. Provide an ability to verify host identity using an SSHFP (SSH Fingerprint) DNS record with DNSSEC signing to prevent DNS spoofing. When disabled, it is still possible to use SSHFP but DNSSEC validation won't be available.

It is recommended to enable the flag if the target system will ever be connecting to SSH servers with an SSHFP record published via a DNSSEC capable server. Otherwise it can be safely disabled.

### libedit
Pass the `--with-libedit` option to the configure script. Provide a history and a line editing features for `sftp` program.

This flag can be safely disabled.

### livecd
Change the `PermitRootLogin` option to `Yes` in an `sshd_config` file.

It is safe to disable the flag as it is only used for building SSH daemon for a Live CD.

### pam
Pass the `--with-pam` option to the configure script. Modify a default `sshd_config` config file to enable PAM related options. Provide PAM stack support for SSH server to have an additional control over user authentication procedures. It can be used to improve security, e.g. to set-up two-factor authentication.

It is safe to disable this flag if there is no need to use PAM stack.

### pie
Pass the `--with-pie` option to the configure script. Append an `-fPIE` option to a `CFLAGS` variable and a `-pie` option to an `LDFLAGS` variable. Build a PIE (position-independent executable) ssh binaries. It can be used with e.g. PaX to randomize an application memory location and thus improve a security.

It is recommended to keep this flag enabled.

### security-key
Pass the `--with-security-key-builtin` option to the configure script. Enable support for FIDO/U2F protocol to allow to configure a hardware security key when authenticating via SSH on a remote server. After a user logs into a server by using their regular credentials, they'll be required to present a FIDO/U2F-based security key (USB, Bluetooth, NFC, etc) as a second proof-of-identity.

This flag can be safely disabled, however is very useful for security-conscious users.

### selinux
Pass the `--with-selinux` option to the configure script. Enable SELinux support for OpenSSH - checking if SELinux is enabled and changing a processes context as necessary.

This flag should only ever be changed system-wide, e.g. by using SELinux-enabled Portage profile.

### ssl
Modify configure scripts to provide an actual `libcrypto` library location obtained from pkg-config. Pass the `--with-openssl` and the `--with-ssl-engine` options to the configure script.

If disabled, internal cryptographic routines will be used instead of OpenSSL. Support only AES-CTR and chacha20+poly1305 ciphers, ECDH/curve25519 key exchange and Ed25519 public keys.

This flag should normally be enabled, unless target system will never use routines outside of outlined above.

### static
Conflicts with `pie`. Append the `-static` option to the `LDFLAGS` variable. Build and install statically linked binaries.

It is recommended to keep this flag disabled unless there is an explicit need for static SSH binaries.

### test
Execute a test-suite provided together with a source code. This will extend a build time.

The flag should normally be disabled as it is only useful for the Gentoo team, developers or testers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### X
Pull a [x11-apps/xauth](../x11-auth/xauth.md) package as a dependency. It is necessary for `X11Forwarding` to securily access GUI on a remote server via SSH protocol.

It is recommended to disable this flag unless there is a need to use X11 Forwarding functionality, especially because there are know vulnerabilities associated with the feature.

### xmss
Append the `-DWITH_XMSS` option to the `CFLAGS` variable. Enable experimental support for PQC (Post Quantum Crypto) XMSS keys that are using the stateful hash-based signature scheme (RFC 8391).

This flag should be disabled, unless there is a need to use XMSS keys.
