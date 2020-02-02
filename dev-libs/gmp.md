# dev-libs/gmp

### asm
Pass the `--enable-assembly` option to the configure script. Use an optimized assembly code for the most common inner loops over plain C code to improve performance.

This flag should normally be enabled as it provides a performance boost.

### cxx
Pass the `--enable-cxx` option to the configure script. Build and install a `libgmpxx` library and a `gmpxx.h` header. Enable a C++ support: provide classes, input/output and string conversion operators, etc.

It is recommended to enable this flag.

### doc
Install a `gmp-man-<VERSION>.pdf` documentation into a `/usr/share/doc/gmp-man-<VERSION>` directory.

This flag can be safely disabled.

### pic
Pass the `--with-pic` option to the configure script. Build the `libgmp` shared library with PIC (Position Independent Code) enabled. This will have a small overhead on each function call and global data address.

This flag can be enabled to improve security in expense of small performance hit.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libgmp` library (and a `libgmpxx` library if the `cxx` flag is also enabled).

This flag should normally be disabled, unless there is an explicit need for the static libraries.
