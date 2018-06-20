# sys-libs/pam
### audit
Passes the `--enable-audit` option to the configure script. This will build and install the `pam_audit` module that allows reporting PAM events via the Kernel Audit Subsystem. The `pam_loginuid` module gains an ability to prevent logins if an `auditd` is not running or crashed.

It is safe to disable this flag unless there is a need for auditing support. It can be useful for debugging issues with SELinux and AppArmor profiles.

### berkdb
The flag passes the `--enable-db` option to the configure script. This will build and install `pam_userdb` module that allows authentication against a db database.

This flag can be safely disabled.

### cracklib
Passes the `--enable-cracklib` option to the configure script. Provides the `pam_cracklib` module that can enforce a password complexity and verify passwords against a dictionary attack.

It is safe to disable this flag.

### debug
This flag passes the `--enable-debug` to the configure script. Provides the `pam_debug` module that is useful for PAM stack debugging.

It is recommended to disable this flag unless there is a need to debug problems with PAM.

### filecaps
The flag instructs a build to add `CAP_DAC_OVERRIDE` capability to the `unix_chkpwd` binary so it can access `/etc/shadow` without having suid bit set.

It is recommended to keep this flag enabled.

### nis
Passes the `--enable-nis` option to the configure script. Enables a NIS (Network Information Services) authentication support in the `pam_unix` module.

This flag should generally be disabled, because nowadays a LDAP is preferred over NIS.

### nls
The flag passes the `--enable-nls` option to the configure script. Enables support for message translations using gettext. An example of translated message is a password expiry notice.

It is safe to disable this flag unless there is a desire for non-English messages.

### pie
Passes the `--enable-pie` option to the configure script. Appends a `-fpie` option to the `CFLAGS` and a `-pie` to the `LDFLAGS` to produce PIE (Position Independent Executables) libraries and binaries. This is also used as a security feature.

It is recommended to keep this flag enabled.

### selinux
The flag passes the `--enable-selinux` option to the configure script. Provides a SELinux support for a PAM stack. Enables reporting via the Kernel Audit Subsystem for SELinux restrictions if `audit` flag is also enabled.

This flag should only be enabled systemwide as part of the selinux-enabled Gentoo profile.

### test
Executes test suite provided with a source code after a build is complete. This will extend a build time.

This flag should be disabled. It is only useful for the Gentoo team, developers or testers.
