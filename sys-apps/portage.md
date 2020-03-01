# sys-apps/portage

### apidoc
Add the `apidoc` target to the list of tagets that are passed to `setup.py`. Use the Sphinx Python documentation tool to generate API documentation from the source code.

This flag can be safely disabled if there is no need for Portage Python API documentation.

### build
This flag should normally be disabled. It is used by the Gentoo team to create early build stages and bootstrapping. Under the hood it will ignore a number of flags and dependencies as well as disable the rsync verification.

### doc
Generate and install HTML documentation from DocBook by calling a `make docbook` command followed by a `make install_docbook`. Resulting documentation will be installed into a `/usr/share/doc/portage-<VERSION>/html` directory.

It is safe to disable this flag unless a documentation is necessary.

### gentoo-dev
Disable the `--dynamic-deps` emerge runtime option that is enabled by default. Enable the following additional Portage FEATURES by default: an `ipc-sandbox`, a `network-sandbox` and a `strict-keepdir`.

This flag should normally be disabled. It is mainly used by Gentoo developers.

### ipc
Modify sources to enable a Portage IPC daemon. This daemon is responsible for communication between the main Portage process and a running ebuild. It helps detect dead or stale builds and action on them.

It is recommended to enable this flag as an IPC functionality is mature enough nowadays and helps with various edge cases.

### native-extensions
Compiles native C language extensions to improve portage performance. If disabled a Python code is used instead.

Enabling this flag is recommended for performance reasons. It can be disabled temporarily, e.g. for bootstrapping or while cross-compilling.

### rsync-verify
Enable cryptographic verification of the Portage tree during sync. It is a security feature that prevents tempering or hijacking of the portage tree for various mirrors.

It is highly recommended to enable the flag, especially on production server environments.

### selinux
Pull in the [sys-libs/libselinux](../sys-libs/libselinux.md) package as a dependency and ensure that it has a `python` flag set that provides a `selinux` Python module. Allow portage to work properly in a SELinux-enabled environment and properly manipulate security contexts.

This flag should only be ever toggled system-wide, e.g. as part of SELinux-enabled Portage profile.

### xattr
Enable `xattr` Portage feature by default (but only on Linux system). Ensure that all portage operations are handling XATTRs (eXtended ATTRibutes) properly, e.g. `tar` archives are extracted using a `--xattrs` option.

This flag should be toggled system-wide only. Enabling this flag on individual packages might and will result into lost XATTRs.
