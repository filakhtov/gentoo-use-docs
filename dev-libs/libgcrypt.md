# dev-libs/libgcrypt

### asm
By default, libgcrypt will be built with assembler optimizations, i.e. using the manually optimized assembler code for MPI (multi-precision-integers) and cipher calculations instead of relying on compiler optimizations. When this flag is disabled, pass the `--disable-asm` option to the configure script to disable these optimizations.

It is recommended to enable this flag for perfomance improvements.

### doc
Invokes the `make -C doc gcrypt.pdf` build command. This produces a PDF documentation file that will be installed into the `/usr/share/doc/libgcrypt-<VERSION>` directory. The `virtual/texi2dvi` package will be pulled in as a dependency and is required for building the documentation.

It is safe to disable this flag.

### getentropy
Pass the `--enable-random=getentropy` (`linux` if the flag is disabled) option to the configure script. Use the `getentropy()` function that requires `getrandom()` syscall which is available starting from Linux kernel 3.17 and provides high quality cryptographic random byte generation. When the flag is disabled, `libgcrypt` will try `getrandom()`, but if it fails fall back to reading `/dev/random`.

This flag should be enabled on systems with modern Linux kernels.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgcrypt` library.

This flag should only be enabled if there is an explicit need for this static library, e.g. for development purposes.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
