# sys-devel/flex

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate programs messages into various languages.

It is safe to disble the flag unless there is a need to use programs in a non-Enlish language.

### static
Append a `-static` option to the `LDFLAGS` variable for the duration of the build. Build and install a statically linked `lex`, `flex` and `flex++` binaries.

This flag should only be enabled if there is an explicit need for the static binaries.

### test
Execute a `make check` command when the main build is complete. When disabled, patch a `Makefile.am` to remove `tests` directory from build target. Run a test suite provided with the source code.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
