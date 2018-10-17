# dev-python/beautifulsoup

### doc
Execute the `make html` command from the `doc` source subdirectory. Use the Python Sphinx documentation generator to produce documentation in the HTML format and install it into the `/usr/share/doc/beautifulsoup-<VERSION>/html` directory. Documentation contains library description, quick start guide, installation, API documentation, etc.

It is safe to disable the flag.

### test
Execute the `nosetest --verbose -w lib` command when the main build script is completed. Use the Python Nose testing framework to run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, as it is mainly useful for the Gentoo team, testers or developers.
