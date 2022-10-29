# sys-process/psmisc

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support for the `-4`, `-6`, `--ipv4` and `--ipv6` runtime options for `fuser` tool. Provide an ability to look for IPv6 sockets.

This flag can be safely disabled. It should be enabled if the system to be participating in IPv6 capable networks.

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate program messages based on the system locale and install appropriate translation files.

It is safe to disable the flag unless there is a need to use program in a non-Enlish language.

### selinux
Pass the `--enable-selinux` option to the configure script. Enable `-Z` option runtime support in `pstree` tool to obtain and display SELinux security contexts.

This flag should only ever be toggled system-wide, e.g. as part of a SELinux-enabled Portage profile.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### X
Install a `pstree.x11` symlink to a `pstree` program. When `pstree` is executed via this symlink it will wait for a keypress before exiting (so that terminal window will stay open to read an output).

It is safe to disable the flag, as there are usually GUI tools to list running processes under Desktop Environment.
