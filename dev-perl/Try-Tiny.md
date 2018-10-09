# dev-perl/Try-Tiny

### minimal
The `Try-Tiny` module can optionally use `Sub::Name` module to name the try/catch/finally blocks when available, so this flag, if disabled, will pull the [dev-perl/Sub-Name](../dev-perl/Sub-Name.md) package as a dependency to provide it. Enabling this flag will skip this optional dependency.

This flag should be disabled if there is a need to use named try/catch/finally blocks.

### test
Execute the `make test` command from the source directory after the main build is completed to run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, because it is mainly useful for the Gentoo team, testers and developers.
