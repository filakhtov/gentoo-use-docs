# sys-apps/debianutils

### installkernel
Pull in the [sys-kernel/installkernel-gentoo](../sys-kernel/installkernel-gentoo.md) and [sys-kernel/installkernel-systemd-boot](../sys-kernel/installkernel-systemd-boot.md) packages as a dependency to provide the `/sbin/installkernel` script that is required for installing kernel via the `make install` command.

It is recommended to keep this flag enabled.

### static
Append a `-static` option to the `LDFLAGS` variable for a duration of the build. Build and install a statically linked version of `run-parts` and `tempfile` binaries.

This flag should only be enabled if there is an explicit need for the static binaries.
