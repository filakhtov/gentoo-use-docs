# sys-apps/pciutils

### dns
Pass the `DNS=yes` variable to the `make` command. Enable support for querying the central database of PCI IDs using a DNS protocol.

It is safe to disable this flag, in which case newer devices that aren't available in a local database yet won't be properly identified, e.g. by an `lspci` command.

### kmod
Pass the `LIBKMOD=yes` variable to the `make` command. Provide an ability for an `lspci` command to display a kernel module that is used for the particular device and a list of available alternatives.

This flag can be safely disabled.

### static-libs
Make a copy of the source directory to perform an additional build. Execute a `make lib/libpci.a` command and pass the `SHARED=no` variable to it. Build and install a statically linked `libpci` library.

The flag should normally be disabled, unless there is an explicit need for a static library.

### udev
Pass the `HWDB=yes` variable to the `make` command. Allow an `lspci` command to lookup unknown PCI device ids inside of a UDEV HWDB database.

This flag can be safely disabled.

### zlib
Pass the `ZLIB=yes` variable to the `make` command. Enable support for a Gzip compressed `pci.ids.gz` database file using a `libz` library.

It is safe to disable the flag.
