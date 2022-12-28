# cpio

### gnu
Use the [app-arch/cpio](../app-arch/cpio.md) package as a provider for cpio. Use the GNU cpio implementation. This is a default choice.

### libarchive
Use the [app-arch/libarchive](../app-arch/libarchive.md) package as a provider for cpio. Use command line tools provided with the `libarchive` a multi-format archive and compression library.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory and binaries into the `/bin`, instead of the `/usr/lib` and `/usr/bin` directories, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.
