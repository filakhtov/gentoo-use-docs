# sys-apps/keyutils

### static
Patch a `Makefile` file and insert a `RPATH = -static` variable and export a `NO_ARLIB=0` variable into an environment. Build and install statically linked binaries: `keyctl`, `request-key` and `key.dns_resolver`.

This flag should only ever be enabled if there is an explicit need for the static binaries.

### static-libs
Export a `NO_ARLIB=0` environment variable before installing the package. Build and install a statically linked version of a `libkeyutils` library.

This flag should only ever be enabled if there is an explicit need for the static library.

### test
Check a kernel configuration, prepare an environment for running test. Execute a `make test` command to run a test suite provided with the source code after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for developers, testers or the Gentoo team.
