# sys-auth/polkit

### daemon
Build and install the `polkitd` daemon that provides the `org.freedesktop.PolicyKit1` D-Bus service, allowing to apply policies and rules to allow applications to request elevated privileges. If this flag is disabled, pass the `-Dlibs-only=true` option to the meson build script to avoid building and installing this daemon binary.

This flag should normally be enabled, otherwise PolKit authorization won't work.

### duktape
Pass the `-Djs_engine=duktape` (instead of the default `mozjs` one) to the Meson build script. Use the Duktape embeddable Javascript engine instead of the SpiderMonkey (Mozilla's JavaScript engine). Duktape is lighter weight and does not depend on outdated Python 2.7 interpreter.

It is recommended to enable this flag.

### examples
Install code examples into a `/usr/share/doc/polkit-<VERSION>/examples` directory. Examples include a C and a Python code.

It is safe to disable this flag.

### gtk
Pull in a [gnome-extra/polkit-gnome](../gnome-extra/polkit-gnome.md) or an [lxde-base/lxsession](../lxde-base/lxsession.md) package as a runtime dependency. These packages provide an authentication agent - a `polkit-gnome-authentication-agent-1` or a `lxpolkit` respectively.

This flag should be enabled if target system to be running a GTK-based or an LXDE-based Desktop Environments.

### introspection
Pass the `-Dintrospection=true` option to the Meson build script. Generate GIR metadata `Polkit-1.0.gir` and `PolkitAgent-1.0.gir` files during the build time to provide dynamic bindings support for languages other than C.

It is safe to disable the flag unless there is an explicit need for GIR files.

### kde
Pull in a [kde-plasma/polkit-kde-agent](../kde-plasma/polkit-kde-agent.md) package as a runtime dependency that provides `polkit-kde-authentication-agent-1`.

This flag should be enabled if target system to be running a KDE-based Desktop Environment.

### pam
Pass the `-Dauthfw=pam` (instead of `shadow`) and `-Dpam_module_dir=` (pointing to the PAM modules directory) options to the Meson build script. Enable integration with a PAM stack while asking for elevated permissions via `pkexec`.

It is recommended to enabled this flag so that polkit honours PAM settings.

### selinux
Pull in a [sec-policy/selinux-policykit](../sec-policy/selinux-policykit.md) as a runtime dependency. Install SELinux policies for a polkit authorization manager.

This flag should ever be toggled system-wide, i.e. as part of a SELinux-enabled Portage profile.

### systemd
Pass the `-Dsession_tracking=libsystemd-login` (instead of the `libelogind` when disabled) option to the Meson build script. Enable integration with a SystemD logind (systemd-logind) daemon for session tracking, instead of a default elogind daemon.

This flag should generally be toggled system-wide, e.g. as part of SystemD Portage profile.

### test
Pass the `-Dtests=true` option to the Meson build script to build the test suite provided with the source code, then run a `meson test` command after the main build is completed to execute a test suite provided with the source code and check for any regressions. This will extend a build time.

This flag should normally be disabled as it is only useful for the maintainers, developers and testers.
