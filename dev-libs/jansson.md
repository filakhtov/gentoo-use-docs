# dev-libs/jansson

### doc
Execute the `make html` command to produce documentation in the HTML format using the Sphinx documentation generator and install it into the system.

It is safe to disable this flag.

### static-libs
Passs the `--enable-static` option to the configure script. Build and install a statically linked version of the `libjansson` library.

This flag should only ever be enabled if there is a need for the static library.
