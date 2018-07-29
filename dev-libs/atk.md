# dev-libs/atk

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `Atk-1.0.gir` GIR metadata file and compile a typelib from it during a build time to provide dynamic bindings support for languages other than C.

This flag can be safely disabled.

### nls
Pull the [sys-devel/gettext](../sys-devel/gettext.md) package as a dependency. The Gettext library is used to provide translation for library messages into various languages based on system locale settings.

This flag should be enabled if there is a need to use non-English languages.

### test
Execute the `make check` command after the main build is completed. Run a test suite provided by the source code. This will extend a build time. When disabled, patch `Makefile` files to exclude the `tests` directory from being built.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
