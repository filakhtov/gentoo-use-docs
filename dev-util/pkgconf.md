# dev-util/pkgconf

### pkg-config
Create a dependency conflict with other packages that provide `pkg-config` functionality and create a `/usr/bin/pkg-config` symlink that points to the `pkgconf` binary.

This flag should normally be enabled to make `pkgconf` a system default implementation of the `pkg-config`.

### test
Unset `pkg-config` related environment variables and execute the `make check` command when the main build is completed to run the test suite provided with the source code and check for regressions. Doing so will extend the overall build time.

This flag should normally be disabled as executed tests are primarily useful for package maintainers, developers and testers.
