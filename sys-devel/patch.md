# sys-devel/patch

### static
Append a `-static` option to the `LDFLAGS` variable for a duration of the build. Build and install a statically linked `patch` binary.

This flag should only be enabled if there is a need for the static binary.

### test
Execute a `make check` command once the main build is completed. Run a test suite provided with a source code.

This flag should be disabled as it is only useful for the Gentoo team, testers and developers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### xattr
Pass the `--enable-xattr` option to the configure script. Provide an ability to copy eXtended ATTRibutes from an original files into a backup file.

It is recommended to toggle the flag system-wide, otherwise XATTRs might be lost during certain operations.
