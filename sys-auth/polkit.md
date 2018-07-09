# sys-auth/polkit

### elogind
Pass the `--enable-libelogind` option to the configure script. Use a `libelogind` library to track session via elogind instead of default ConsoleKit.

This flag should only be enabled if there is a need to use elogind as a session manager.

### examples
Install code examples into a `/usr/share/doc/polkit-<VERSION>/examples` directory. Examples include a C and a Python code.

It is safe to disable this flag.

### gtk
Pull in a [gnome-extra/polkit-gnome](../gnome-extra/polkit-gnome.md) or an [lxde-base/lxsession](../lxde-base/lxsession.md) package as a runtime dependency. These packages provide an authentication agent - a `polkit-gnome-authentication-agent-1` or a `lxpolkit` respectively.

This flag should be enabled if target system to be running a GTK-based or an LXDE-based Desktop Environments.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate GIR metadata files during a build time to provide dynamic bindings support for languages other than C.

It is safe to disable the flag unless there is an explicit need for GIR files.

### jit
This flag does nothing.

### kde
Pull in a [kde-plasma/polkit-kde-agent](../kde-plasma/polkit-kde-agent.md) package as a runtime dependency that provides `polkit-kde-authentication-agent-1`.

This flag should be enabled if target system to be running a KDE-based Desktop Environment.

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate program messages to a system locale language.

It is safe to disable this flag if there is no need for non-English languages.

### pam
Pass the `--with-pam-module-dir`, and the `--with-authfw=pam` (instead of `shadow`) options to the configure script. Enable integration with a PAM stack while asking for elevated permissions via `pkexec`.

It is recommended to enabled this flag so that polkit honours PAM settings.

### selinux
Pull in a [sec-policy/selinux-policykit](../sec-policy/selinux-policykit.md) as a runtime dependency. Install SELinux policies for a polkit authorization manager.

This flag should ever be toggled system-wide, i.e. as part of a SELinux-enabled Portage profile.

### systemd
Pass the `--enable-libsystemd-login` option to the configure script. Enable integration with a SystemD logind (systemd-logind) daemon for session tracking, instead of a default ConsoleKit daemon.

This flag should generally be toggled system-wide, e.g. as part of SystemD Portage profile.

### test
Pass the `--enable-test` option to the configure script. Run a `make check` command during a build. Execute a test suite provided with a source code. This will extend a build time.

This flag should normally be disabled as it is only useful for the Gentoo team, developers and testers.
