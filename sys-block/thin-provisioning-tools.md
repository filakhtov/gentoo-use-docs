# sys-block/thin-provisioning-tools

### static
Append a `-static` option to the `LDFLAGS` variable for a duration of the build. Build and install statically linked `thin_dump`, `thin_restore`, `thin_check`, etc binaries.

This flag should only be enabled if there is a need for static binaries.

### test
Pass the `--enable-testing` option to the configure script. Execute a `make unit-test` command after the main build is completed. Run a test suite provided with the source code. This will extend a build time.

This option should normally be disabled as it is primarily useful for the Gentoo team, testers and developers.
