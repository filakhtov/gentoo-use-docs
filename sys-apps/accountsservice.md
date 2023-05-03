# sys-apps/accountsservice

### doc
Pass the `-Ddocbook=true` option to the meson build script. Use the xmlto utility to generate additional documentation in an HTML format that provides D-Bus API documentation for `AccountsService` service.

It is safe to disable the flag.

### elogind
Can not be used together with the `systemd` flag. Pass the `-Delogind=true` option to the meson build script. Integrate AccountsService with the elogind service to query and manage login sessions and seats.

This flag should be enabled if there is a need to run the AccountsService with elogind.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc tools to generate the `libaccountsservice` API documentation and install it into the `/usr/share/gtk-doc/html/accountsservice` directory.

It is safe to disable the flag.

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate the `AccountsService-1.0.gir` GIR metadata file during the build to provide dynamic bindings for languages other than C using the GObject Introspection.

It is safe to disable the flag.

### selinux
Pull the [sec-policy/selinux-accountsd](../sec-policy/selinux-accountsd.md) package as a dependency to install SELinux policies necessary for the AccountsService to run properly under the SELinux-restricted kernel.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### systemd
Can not be used together with the `elogind` flag. Integrate AccountsService with the SystemD LoginD to query and manage login sessions and seats.

This flag should be enabled on systems that use systemd as their init system.

### test
Build the test suite provided with the source code and execute the `meson test` command to run it after the main build is completed to check for any regressions. This will extend the build time. When this flag is disabled, patch the `meson.build` script to disable the test suite build.

This flag should normally be disabled, because the test suite is primarily oriented towards the developers, maintainers and testers.
