# dev-python/pycairo

### doc
Execute the `make` command inside of the `docs` subdirectory of the source tree. Use the Sphinx documentation generation tool to build additional documentation in an HTML format and install it into the `/usr/share/doc/pycairo-<VERSION>/html` directory.

It is safe to disable the flag.

### examples
Install Python source code example files that demonstrate how to use Cairo module for variety of different use cases into the `/usr/share/doc/pycairo-<VERSION>/examples` directory. Examples include small game, filling, stroking, drawing curves, ellipses, etc.

This flag can be safely disabled.

### test
Execute the `setup.py test` command after the main build is completed to aun a test suite provided with the source code and check for regressions. This will extend a build time.

This flag should normally be disabled as it is primarily used by the maintainers, testers and developers.
