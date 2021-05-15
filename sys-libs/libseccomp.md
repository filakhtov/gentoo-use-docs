# sys-libs/libseccomp

### python
Run the `setup.py` script from the `src/python` subdirectory to configure the Python bindings for `libseccomp` library, then run `make` to build and `make install` to install the `seccomp` Python module that provides an API for the Linux Kernel's syscall filtering capability, seccomp.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libseccomp` library.

This flag should only be enabled if there is a need for the static library.
