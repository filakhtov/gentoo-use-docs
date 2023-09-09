# sys-apps/kbd

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translat programs messages into various languages using a Gettext library.

This flag can be safely disabled unless there is a need to use a non-English language.

### pam
Pass the `--enable-vlock` option to the configure script. Build and install a `vlock` binary that can lock virtual console while saving a current session.

It is safe to disable the flag.

### selinux
Pull in the [sec-policy/selinux-loadkeys](../sec-policy/selinux-loadkeys.md) package as a dependency that contains policies required for the `loadkeys` command to work under the SELinux-enabled kernel.

This flag should only ever be enabled system-wide as part of the SELinux-enabled profile.

### test
Pass the `--enable-tests` option to the configure script. Execute a `make check` command once the main build is completed. Execute a test suite provided with a source code. This will extend a build time.

This flag should normally be disabled because it is mainly useful for the Gentoo team, developers and testers.
