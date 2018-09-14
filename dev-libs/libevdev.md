# dev-libs/libevdev

### doc
Generate additional documentation in the HTML format using the Doxygen tool and install it into the `/usr/share/doc/libevdev-<VERSION>/html` directory.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libevdev` library.

This flag should only be enabled if there is an explicit need for the static library.
