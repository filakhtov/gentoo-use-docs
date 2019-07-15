# sys-apps/file

### python
Build and install a `magic` Python module, `libmagic` bindings for Python.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked libraries.

The flag can be safely disabled.

### zlib
Pass the `--enable-zlib` option to the configure script. It enables an internal handling of a zlib compression for systems that have `zlib.h`, but do not provide a library to link against (i.e. Android).

This flag should be disabled as it doesn't do anything on a Linux system.
