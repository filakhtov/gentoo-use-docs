# app-admin/sudo

### gcrypt
Pass the `--enable-gcrypt` option to the configure script. Use the `libgcrypt` library to compute the SHA-2 digest of the command before it is executed for entries in the sudoers file that have `Digest_Spec` prefix configured.

It is safe to disable this flag.

### ldap
Pass the `--with-ldap` and `--with-ldap_conf_file=/etc/ldap.conf.sudo` options to the configure script. Enable support for LDAP (Lightweight Directory Access Protocol) to allow querying access rules from LDAP server, instead of the `sudoers` file. This can be especially useful for synchronizing sudoers in a large, distributed environment.

This flag should only be enabled if there is a need to use LDAP for storing and providing sudoers rules.

### nls
Pass the `--enable-nls` option to the configure script. Enable support for NLS (Native Language Support) to allow displaying informational, warning and error strings translated into the native language of the program's users, based on the system locale and configuration.

It is safe to disable this flag.

### offensive
Pass the `--with-insults` and `--with-all-insults` options to the configure script. Print an insulting message to the user when they enter an incorrect password.

This flag can be safely disabled.

### pam
Pass the `--with-pam` and `--with-pam-login` options to the configure script. Enable integration with PAM (Pluggable Authentication Modules) system and enable specific PAM-based session. This allows to use PAM stack when authenticating a user before executing a command using `sudo`.

It is safe to disable this flag if there is no need to use PAM modules for authentication with `sudo`.

### sasl
Pass the `--enable-sasl` option to the configure script. Enable support for the SASL (Simple Authentication and Security Layer) framework to allow to authenticate when `sudo` is communicating with a LDAP (Lightweight Directory Access Protocol) server, instead of using anonymous connection.

This flag should normally be disabled.

### secure-path
Pass the `--with-secure-path` option to the configure script and specify expected safe paths as a value. Enabling this flag will make `sudo` reset the `PATH` variable before invoking the command and allows to avoid malicious path injections.

Enabling this flag will improve security, but might cause unexpected issues at runtime.

### selinux
Pass the `--with-selinux` option to the configure script. Enabled SELinux RBAC (Role-based access control) support and allow `sudo` to properly execute commands with elevated privileges when running on a SELinux-enabled system.

This flag should only be enabled system-wide on a SELinux-capable system.

### sendmail
Pass the `--with-sendmail` option to the configure script. Provide an ability to configure sending notification emails when a command is executed using `sudo` or user authentication fails.

It is safe to disable this flag.

### skey
Pass the `--with-skey` option to the configure script. Enable support for S/Key (Single use password) authentication mechanism.

This flag should normally be disabled.

### ssl
Pass the `--enable-openssl` option to the configure script. Use the OpenSSL library to compute the SHA-2 digest of the command before it is executed for entries in the sudoers file that have `Digest_Spec` prefix configured.

It is safe to disable this flag.

### sssd
Pass the `--with-sssd` option to the configure script. Enable integration with sssd (System Security Services Daemon) to allow using it as a source for `sudo` rules and enable support for rule caching mechanism in sssd.

This flag should only be enabled if there is a need to use sudo with SSSD.
