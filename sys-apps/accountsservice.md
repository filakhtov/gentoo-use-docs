# sys-apps/accountsservice

### doc
Pass the `--enable-docbook-docs` option to the configure script. Generate additional documentation in an HTML format, including the `libaccountsservice` API documentation using the xmlto and GTK-Doc tools.

It is safe to disable the flag.

### elogind
Pass the `--enable-elogind` option to the configure script. Integrate AccountsService with the elogind service to query and manage login sessions and seats.

This flag should be enabled if there is a need to run the AccountsService with elogind.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `AccountsService-1.0.gir` GIR metadata file during the build to provide dynamic bindings for languages other than C using the GObject Introspection.

It is safe to disable the flag.

### selinux
Pull the [sec-policy/selinux-accountsd](../sec-policy/selinux-accountsd.md) package as a dependency to install SELinux policies necessary for the AccountsService to run properly under the SELinux-restricted kernel.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### systemd
Pass the `--enable-systemd` option to the configure script. Integrate AccountsService with the SystemD LoginD to query and manage login sessions and seats.

This flag should be enabled if there is a need to run the AccountsService with the SystemD init ecosystem.
