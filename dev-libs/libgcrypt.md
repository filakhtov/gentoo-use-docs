# dev-libs/libgcrypt

### asm
By default, libgcrypt will be built with assembler optimizations, i.e. using the manually optimized assembler code for MPI (multi-precision-integers) and cipher calculations instead of relying on compiler optimizations. When this flag is disabled, pass the `--disable-asm` option to the configure script to disable these optimizations.

It is recommended to enable this flag for perfomance improvements.

### doc
Invokes the `make -C doc gcrypt.pdf` build command. This produces a PDF documentation file that will be installed into the `/usr/share/doc/libgcrypt-<VERSION>` directory. The `virtual/texi2dvi` package will be pulled in as a dependency and is required for building the documentation.

It is safe to disable this flag.

### o-flag-munging
Passes the `--enable-O-flag-munging` option to the configure script. This option modifies compiler flags to set a lower optimization mode for some very complex code in order to prevent breaking a build. It is not necessary in most cases.

This flag should only be enabled if there are any problems compiling the library.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgcrypt` library.

This flag should only be enabled if there is an explicit need for this static library, e.g. for development purposes.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
