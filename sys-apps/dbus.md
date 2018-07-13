# sys-apps/dbus

### debug
Pass the `--enable-verbose-mode` and the `--enable-stats` options to the configure script. Log a lot of additional debugging information at runtime. Provide an ability to collect and report bus statistics information on a memory usage, a number of messages passed, a number of active connections and so forth.

This flag should normally be disabled because it increases a library size, decreases a performance and might increase a security risk.

### doc
Pass the `--enable-doxygen-docs` option to the configure script. Generate and install an API documentation for D-Bus library using source code annotations.

It is safe to disable this flag, unless there is a need for low-level API documentation.

### elogind
Pass the `--enable-elogind` option to the configure script. Provide an integration with the elogind session management daemon to track user logins between different seats and consoles.

This flag should only be enabled if the target system to be using elogind.

### selinux
Pass the `--enable-selinux` and the `--enable-libaudit` options to the configure script. Add a `/selinux/access` path to the sandbox allowed write list required for building. Enable a proper operation under a SELinux restricted kernel. Check security context of the sender and receiver and verify that SELinux security controls allow the message to be sent to a particular connection. Use a `libaudit` library to report AVC denials via Kernel Audit Subsystem.

This flag should ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libdbus-1` library.

It is safe to disable this flag unsless there is an explicit need for a static library.

### systemd
Pass the `--enable-systemd` option to the configure script. Provide an integration with SystemD's logind to track user logins between different seats and consoles.

The flag should only be enabled if the target system to be used with SystemD.

### test
Run a configure script in designated test directory and pass the `--enable-asserts`, the `--enable-checks` and the `--enable-embedded-tests` options to it. Run a `make` command inside of the same directory afterwards. When a main build is completed, execute a `make check` command inside of the same directory. This will extend a build time.

This flag should normally be disabled as it is only useful for the Gentoo team, testers and developers.

### user-session
Pass the `--enable-user-session` option to the configure script. This might break some dbus consumers that aren't prepared for the change, see [Gentoo Bug #576028](https://bugs.gentoo.org/576028) for details. Start a session-wide `dbus` systemd service and socket as part of the SystemD user instance that will be shared across different seats and consoles for the same user.

It is recommended to enable this flag if the target system uses SystemD and there is a need to run a modern desktop environment.

### X
Pass the `--with-x` option to the configure script. Install an `80-dbus` script into a system `xinitrc.d` directory that is responsible for automatically launching a session dbus instance as part of an X.org startup.

This flag is necessary if there is a need to run a desktop environment without the SystemD.
