# net-libs/libmnl

### examples
Install additional example files into a `/usr/share/doc/libmnl-<VERSION>/examples` directory. Provide various examples how to use the library written in a C language.

This flag should normally be disabled.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libmnl` library.

The flag should only be enabled if there is a need for the static library.
