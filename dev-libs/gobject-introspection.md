# dev-libs/gobject-introspection

### cairo
Pass the `--with-cairo` option to the configure script. This flag only makes sense when a `test` flag is enabled. Use a Cairo library to enable building and executing additional test cases.

This flag should be normally disabled.

### doctool
Pass the `--enable-doctool` option to the configure script. Build and install a `g-ir-doc-tool` tool for generating documentation from comments and annotations in the source code.

It is safe to disable the flag.

### test
Execute a `make check` command once the main build is completed. Run a test suite provided with the code base. This will extend the build time.

This flag should normally be disabled as it is only useful for the Gentoo team, testers and developers.
