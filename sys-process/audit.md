# sys-process/audit

### gssapi
Pass the `--enable-gssapi-krb5` option to the configure script. Enable GSSAPI Kerberos 5 support that can be used for authentication and encryption when sending audit events to an external system.

It is safe to disable the flag.

### ldap
When the flag is enabled, the `audispd-zos-remote` remote auditing-plugin that forwards incoming audit events to a z/OS SMF (Service Management Facility) database using the ITDS (IBM Tivoli Directory Server) will be built and installed. If the flag is disabled, the `configure.ac` and `Makefile.am` files will be patched to skip the plugin build.

This flag can be safely disabled.

### python
Build and install Python bindings for the `libaudit` library for every active python implementation. These bindings provide the `auparse` module that is used to parse Audit event messages.

It is safe to disable the flag.

### split-usr
When enabled, install produced shared libraries into the `/lib` directory instead of `/usr/lib`, so that they are available at the early boot stage, before `/usr` partition is mounted.

This flag should only be enabled if the system has a separate `/usr` partition.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install the statically linked version of the `libaudit` and `libauparse` libraries.

This flag should only ever be enabled if there is an explicit need for these static libraries.
