# dev-libs/libxdg-basedir

### doc
Pass the `--enable-doxygen-html` option to the configure script. Use the Doxygen tool to generate additional documentation in the HTML format and install it into the `/usr/share/doc/libxdg-basedir-<VERSION>/html` directory. This documentation is intended for developers who plan to use the library.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libxdg-basedir` library.

This flag should only be enabled if there is an explicit need for the static library.
