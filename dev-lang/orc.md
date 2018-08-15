# dev-lang/orc

### examples
Install additional example source code, in both - C and Orc languages, showing various usages of the `liborc` library, into the `/usr/share/doc/orc-<VERSION>/examples` directory.

It is safe to disable the flag.

### pax_kernel
Disable PaX MPROTECT restrictions by setting an `m` flag on the `orc-bugreport` and `orcc` binaries and the `liborc` and `liborc-test` libraries required for applications linked against the `liborc` to properly run under a PaX-restricted Kernel.

This flag should only be enabled if the target system is running a PaX-enabled Kernel.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `liborc` library.

This flag should only be enabled if there is a need for the static library.
