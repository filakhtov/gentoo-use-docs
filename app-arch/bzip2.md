# app-arch/bzip2

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static
Pass the `-static` option to the `make` command. Build and install statically linked binaries, e.g. a `bzip2`, a `bunzip2`, a `bzcat`, etc.

This flag should normally be disabled unless there is a need for static binaries.

### static-libs
Build and install statically linked `libbz2.a` library.

This flag should be disabled unless there is a need for static library.
