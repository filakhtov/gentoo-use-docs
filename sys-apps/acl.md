# sys-apps/acl

### nls
Pass the `--enable-gettext` option to the configure script. Use a Gettext library to translate programs messages and a library output into various languages based on the system locale settings.

This flag should be enabled if there is a need to use any non-English languages.

### split-usr
Install the `libacl` library into the `/lib` directory instead of `/usr/lib` prefix in order to ensure that it is available during the early boot process if the `/usr` directory lives on a separate partition.

This flag should be enabled if the system uses separate `/usr` partition.

### static-libs
Pass the `--enable-static` option to the configure script. When disabled, remove all statically linked files. Build and install a statically linked version of the `libacl` library.

The flag should only be enabled if there is a need for the static library.
