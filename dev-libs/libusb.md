# dev-libs/libusb

### udev
Pass the `--enable-udev` option to the configure script.

### debug
Pass the `--enable-debug-log` option to the configure script.

### doc
Execute the `make docs` command from the `doc` source subdirectory. Generate additional API documentation in an HTML format using the Doxygen tool and install it into the `/usr/share/doc/libusb-<VERSION>/html` directory.

This flag can be safely disabled.

### examples
Install additional C source files that show how developers can use the `libusb` library into the `/usr/share/doc/libusb-<VERSION>/examples` directory.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libusb` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Build and install additional test tools. Execute the `make check` command to run a test suite provided with the source code, then execute `stress` command from the `tests` source subdirectory to perform simple stress tests. This will extend a build time.

This flag should normally be disabled as it is primarily used by the Gentoo team, testers and developers.
