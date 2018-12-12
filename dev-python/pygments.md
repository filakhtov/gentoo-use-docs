# dev-python/pygments

### doc
Execute the `make html` command from the `html` subdirectory of the source tree. Use the Sphinx tool to generate documentation in the HTML format and install it into the `/usr/share/doc/pygments-<VERSION>/html` directory. Documentation is oriented towards developer and includes quick start guide, installation process, description of builtin components, API reference, hints and tricks, etc.

It is safe to disable the flag.

### test
Copy the tests directory from the source tree into the build directory. Run the `nosetests` command after the main build is completed to run the test suite provided with the source code to check for regressions. This will extend the build time.

This flag should normally be disabled as it is mainly used by developers, testers, maintainers and not end users.
