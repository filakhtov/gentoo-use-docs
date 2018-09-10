# dev-python/pygtk

### doc
Pass the `--enable-docs` option to the configure script. Generate additional documentation in the HTML format and install it into the `/usr/share/doc/pygtk-<VERSION>/html` directory. The documentation includes reference, API specification and usage examples.

This flag can be safely disabled.

### examples
Install additional example files into the `/usr/share/doc/pygtk-<VERSION>/examples` directory. Example scripts demonstrate how to use ATK accessibility toolkit, how to create an editable graphical interface, how to handle signal processing, how to create simple application with menues, widgets, etc.

It is safe to disable the flag.

### test
Execute the `make check-local` command from an Xvfb based X session after the main build is completed. Run the test suite provided with the source code for every enabled Python implementation. This will extend a build time.

This flag should normally be disabled as it is primarily used by the Gentoo team, developers and testers.
