# dev-python/dbus-python

### doc
Pass the `--enable-documentation` option to the configure script. Use the Sphinx tool to generate an API and development documentation for the `dbus` Python module and install it into the `/usr/share/doc/dbus-python-<VERSION>` directory.

This flag can be safely disabled.

### examples
Install additional example source code into the `/usr/share/doc/dbus-python-<VERSION>/examples` directory. Examples include how to write a simple DBus service and a client, how to emit and handle signals, etc.

It is safe to disable the flag.

### test
For each enabled Python target, execute the `make check` command from the build directory to run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as these test cases are normally useful for the developers, testers or the Gentoo team.
