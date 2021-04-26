# dev-libs/libusb

### debug
Pass the `--enable-debug-log` option to the configure script. Unconditionally set `libusb` logging level to `DEBUG` so that all `INFO`, `WARNING` and `ERROR` messages will be printed. Note: it is NOT possible to request `DEBUG` level messages, despite there being a logging level for it. The author of libusb seems to consider this broken behaviour to be a feature.

This flag should normally be disabled.

### doc
Execute the `make` command from the `doc` source subdirectory. Generate additional API documentation in an HTML format using the Doxygen tool and install it into the `/usr/share/doc/libusb-<VERSION>/html` directory.

This flag can be safely disabled.

### examples
Install additional C source files that show how developers can use the `libusb` library into the `/usr/share/doc/libusb-<VERSION>/examples` directory.

It is safe to disable the flag.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libusb` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Build and install additional test tools. Execute the `make check` command to run a test suite provided with the source code, then execute `stress` command from the `tests` source subdirectory to perform simple stress tests. This will extend a build time.

This flag should normally be disabled as it is primarily used by the Gentoo team, testers and developers.

### udev
Pass the `--enable-udev` option to the configure script. Integrate with udev device manager to enable support for monitoring and handling device events, hot plugging, and provide an ability to obtain additional device information fro udev.

It is recommended to enable this flag on modern systems that use the udev device manager.
