# dev-python/six

### doc
Execute the `make html` command from the `documentation` directory. Use the Python Sphinx documentation generator to produce an HTML API documentation and install it into the `/usr/share/doc/six-<VERSION>/html` directory.

It is safe to disable the flag.

### test
Execute the `py.test` script when the main build script is completed to run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, as it is mainly useful for the Gentoo team, testers or developers.

