# dev-libs/libyaml

### doc
Run the `make html` command to generate additional documentation in the HTML format and install it into the `/usr/share/doc/libyaml-<VERSION>/html` directory. This documentation provides development information, such as list of modules, available data structures, etc.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libyaml` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Execute the `make check` command after the main build is completed to run the regression test suite provided with the source code. This will extend the build time. When disabled, patch the `Makefile` file to remove `tests` directory from being build to save some time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.
