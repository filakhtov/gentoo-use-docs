# dev-libs/dbus-glib

### debug
Pass a `--enable-asserts` option to a configure script. Ensure that a `G_DISABLE_ASSERT` macro is not defined during compilation and therefore enable `g_assert...()` family of runtime asserts.

This flag should only be enabled for debugging purposes.

### static-libs
Pass a `--enable-static` option to a configure script. Build and install a statically linked version of a `libdbus-glib` library.

This flag should only ever be enabled if there is a need for the static library.

### test
Prepare a test build directory and execute `configure` with a `--enable-checks`, `--enable-tests` and `--enable-asserts` options from it, followed by a `make` and a `make check` commands. Build and run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is only beneficial for the Gentoo team, testers and developers.
