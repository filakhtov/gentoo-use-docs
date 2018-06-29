# sys-apps/kmod
### debug
Pass the `--enable-debug` option to the configure script. Print an additional debugging information at runtime, e.g. a source file, a line number, a function name, etc.

This flag should be disabled as it is only required for debugging purposes.

### doc
Run a `gtkdocize` on `libkmod/docs` directory of the source tree. Pass the `--enable-gtk-doc` option to the configure script. Generate and install `libkmod` API documentation.

It is safe to disable this flag because it is only needed by developers who uses a `libkmod` library.

### lzma
Pass the `--with-xz` option to the configure script. Provide support for modules compressed using `LZMA`/`LZMA2` compression formats via xz utils.

This flag can be safely disabled unless kernel modules are compressed in `LZMA` or `LZMA2` format.

### python
Run the configure script with the `--enable-python` option passed and execute `make` afterwards for every enabled python target. Provide a `kmod` Python module.

It is safe to disable this flag unless there is a need to run Python scripts that use a `kmod` module.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked version of a `libkmod` library.

The flag should be disabled unless there is an explicit need for static library.

### tools
Pass the `--enable-tools` option to the configure script. Create appropriate symlinks for a `depmod`, an `insmod`, a `lsmod`, a `modinfo`, a `modprobe` and a `rmmod` tools pointing to the `kmod` binary.

This flag should normally be enabled as these tools are useful for management of Kernel modules.

### zlib
Pass the `--with-zlib` option to the configure script. Enable support for Gzip compressed modules.

This flag should be enabled if Kernel modules of the target system are compressed using gzip.
