# sys-apps/findutils

### nls
Pass the `--enable-nls` option to the configure script. Enable program messages translation into different languages using a Gettext library and install translation files.

It is safe to disable the flag, unless there is a need for non-English languages.

### selinux
Pass the `--with-selinux` option to the configure script. Allow the `find` command to match a security context of a file via the `-context` runtime option and enable `%Z` format specifier for the `-printf` option.

This flag should only be ever toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### static
Append the `-pthread` option to the compiler flags variable and the `-static` option to the `LDFLAGS` variable for the duration of a build. Build and install a statically linked `find` and `xargs` binaries.

It is safe to disable the flag, unless there is an explicit need for static binaries.

### test
Execute a `make check` command during the build. Run a test suite provided with a source code. This will extend a build time.

This flag should normally be disabled as it is mainly used by the Gentoo team, testers and developers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
