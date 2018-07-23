# dev-libs/libaio

### static-libs
A statically linked version of `libaio` library is built and installed by default, so this flag does nothing if enabled. When disabled, patch `Makefile` to remove static library installation rules.

This flag should only be enabled if there is a need for the static library.

### test
Execute a `make partcheck` command after the main build is completed. Run a test suite provided with the source code.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
