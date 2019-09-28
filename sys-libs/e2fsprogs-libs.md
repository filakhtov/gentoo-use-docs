# sys-libs/e2fsprogs-libs

### split-usr
If the flag is enabled all produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Statically linked versions of `libcom_err` and `libss` libraries are built by default, so this flag does nothing if enabled. When disabled, remove these statically linked libraries from an image before installation.

This flag should only be enabled if there is a need for the static libraries.
