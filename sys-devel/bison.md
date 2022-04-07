# sys-devel/bison

### examples
Install example files into the `/usr/share/doc/bison-<VERSION>/examples` directory. When the flag is disabled, remove the `examples` directory from the built image before installing it into the system.

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

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
