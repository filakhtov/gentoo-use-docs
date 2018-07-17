# sys-devel/bison

### examples
Pass the `--enable-examples` option to the configure script. Does nothing when enabled. If disabled, allow to ignore a dependency on Perl (which is only required for tests and examples) during configure step.

It is safe to disable the flag.

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate program messages into different languages. Install translation files.

This flag can be safely disabled, unless there is a need to use non-English languages.

### static
Append a `-static` option to the `LDFLAGS` variable for the duration of a build. Build and install a statically linked binaries.

The flag should be disabled except if there is an explicit need for the static binaries.

### test
Export the `ac_cv_path_PERL=true` variable for the `configure` script. Execute a `make check` command once a build is complete. Run a test suite provided with a soucre code.

This flag should normally be disabled. It is primarily used by the Gentoo team, testers and developers.
