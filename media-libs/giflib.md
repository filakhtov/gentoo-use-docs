# media-libs/giflib

### doc
Execute the `make` command from the `doc` directory. Generate additional documentation in the HTML and plain text formats and install it into the `/usr/share/doc/giflib-<VERSION>` directory, including the API documentation, GIF format reference, information about compression, etc.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgif` library. When disabled, remove all static files before installation.

This flag should only be enabled if there is an explicit need for the static library.
