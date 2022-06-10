# sys-libs/zlib

### minizip
Execute a `make -C contrib/minizip` command during a build. Build and install minizip library that is able to compress and decompress ZIP archives. Also install additional documentation about the library.

This flag can be safely disabled.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libz` library. If disabled `.a` and `.la` files will be removed before installation.

This flag should normally be disabled unless there is an explicit need for static library.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
