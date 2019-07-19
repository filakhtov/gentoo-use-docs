# dev-libs/lzo

### examples
Install C language example source code files of how to use the `liblzo2` library into the `/usr/share/doc/lzo-<VERSION>/examples` directory.

It is safe to disable the flag.

### split-usr
When enabled, produced libraries will be installed into the `/lib` directory (instead of `/usr/lib`) to make sure that they are available during an early system boot, before additional partitions are mounted.

This flag should be enabled if the system has a separate `/usr` partition and can be safely disabled otherwise.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `liblzo2` library.

This flag should only be enabled if there is a need for the static library.
