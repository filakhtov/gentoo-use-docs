# dev-libs/iniparser

### doc
Execute a `make` command inside of a `doc` directory of the source tree. Build an additional documentation in an HTML format and install it into a `/usr/share/doc/iniparser-<VERSION>/html` directory.

It is safe to disable the flag.

### examples
Install additional examples of how to use a library written in C language into a `/usr/share/doc/iniparser-<VERSION>/examples` directory.

This flag can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libiniparser` library.

The flag should only be enabled if there is a need for the static library.
