# sys-libs/pam

### audit
Passes the `--enable-audit` option to the configure script. This will build and install the `pam_audit` module that allows reporting PAM events via the Kernel Audit Subsystem. The `pam_loginuid` module gains an ability to prevent logins if an `auditd` is not running or crashed.

It is safe to disable this flag unless there is a need for auditing support. It can be useful for debugging issues with SELinux and AppArmor profiles.

### berkdb
The flag passes the `--enable-db` option to the configure script. This will build and install `pam_userdb` module that allows authentication against a db database.

This flag can be safely disabled.

### debug
This flag passes the `--enable-debug` to the configure script. Provides the `pam_debug` module that is useful for PAM stack debugging.

It is recommended to disable this flag unless there is a need to debug problems with PAM.

### filecaps
The flag instructs a build to add `CAP_DAC_OVERRIDE` capability to the `unix_chkpwd` binary so it can access `/etc/shadow` without having suid bit set.

It is recommended to keep this flag enabled.

### nis
Passes the `--enable-nis` option to the configure script. Enables a NIS (Network Information Services) authentication support in the `pam_unix` module.

This flag should generally be disabled, because nowadays a LDAP is preferred over NIS.

### pie
Passes the `--enable-pie` option to the configure script. Appends a `-fpie` option to the `CFLAGS` and a `-pie` to the `LDFLAGS` to produce PIE (Position Independent Executables) libraries and binaries. This is also used as a security feature.

It is recommended to keep this flag enabled.

### selinux
The flag passes the `--enable-selinux` option to the configure script. Provides a SELinux support for a PAM stack. Enables reporting via the Kernel Audit Subsystem for SELinux restrictions if `audit` flag is also enabled.

This flag should only be enabled systemwide as part of the selinux-enabled Gentoo profile.

### split-usr
If the flag is enabled all produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.
