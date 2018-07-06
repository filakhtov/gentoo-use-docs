# sys-libs/zlib

### minizip
Execute a `make -C contrib/minizip` command during a build. Build and install minizip library that is able to compress and decompress ZIP archives. Also install additional documentation about the library.

This flag can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libz` library. If disabled `.a` and `.la` files will be removed before installation.

This flag should normally be disabled unless there is an explicit need for static library.
