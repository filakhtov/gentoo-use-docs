# dev-libs/libgcrypt

### doc
Invokes the `make -C doc gcrypt.pdf` build command. This produces a PDF documentation file that will be installed into the `/usr/share/doc/libgcrypt-<VERSION>` directory. The `virtual/texi2dvi` package will be pulled in as a dependency and is required for building the documentation.

It is safe to disable this flag.

### o-flag-munging
Passes the `--enable-O-flag-munging` option to the configure script. This option modifies compiler flags to set a lower optimization mode for some very complex code in order to prevent breaking a build. It is not necessary in most cases.

This flag should only be enabled if there are any problems compiling the library.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgcrypt` library.

This flag should only be enabled if there is an explicit need for this static library, e.g. for development purposes.
