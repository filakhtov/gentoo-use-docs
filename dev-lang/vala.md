# dev-lang/vala

### test
Run the `make check` command from the `tests` source code subdirectory after the main build is completed to run the test suite provided with the source code to check for regressions. This will extend the build time.

This flag should normally be disabled, because these test are primarily useful for developers and maintainers.

### valadoc
Pass the `--enable-valadoc` option to the configure script. Build and install the `valadoc` tool that can be used to generate programming documentation from a library's API using annotations provided in the VAPI or GIR files.

It is safe to disable the flag.
