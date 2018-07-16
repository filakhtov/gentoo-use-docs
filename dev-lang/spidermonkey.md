# dev-lang/spidermonkey

### debug
Pass the `--enable-debug` option to the configure script. Build a JS engine with developer debug info, enable assertions to allow for easier debugging of linked programs.

This flag should be normally disabled as it has performance impact, can crash programs linked against the library and only useful for debugging.

### minimal
When enabled, a `js` command (a JavaScript shell) won't be installed.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked libraries ???.

This flag should be disabled, unless there is an explicit need for static libraries.

### test
Pass the `--enable-tests` option to the configure script. Disable an MPROTECT and a RANDMMAP PaX flags for `jsapi-tests` binary and execute a `make check` command. Run test suite provided with a source code.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
