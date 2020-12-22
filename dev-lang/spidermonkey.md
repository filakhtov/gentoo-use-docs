# dev-lang/spidermonkey

### clang
Use the Clang compiler instead of GCC.

It is safe to disable this flag.

### debug
Pass the `--enable-debug` option to the configure script. Build a JS engine with developer debug info, enable assertions to allow for easier debugging of linked programs.

This flag should be normally disabled as it has performance impact, can crash programs linked against the library and only useful for debugging.

### jit
Pass the `--enable-ion` option to the configure script. Enable the IonMonkey JavaScript JIT (Just-In-Time) compiler for SpiderMonkey - a whole-method JIT with the ability to perform type specialization, function inlining, linear-scan register allocation, dead code elimination and loop-invariant code motion.

This flag should be enabled for platforms that support JIT compilation to improve performance.

### lto
Pass the `--enable-lto` option and `--enable-linker=lld`, if the `clang` flag is enabled, or `--enable-linkerd=gold`, if it is not, to the configure script. Enable link-time optimization (LTO) to run additional compiler routines to improve performance of the resulting binaries and libraries, however this will make it impossible to step through the code using the debugger. Requires `ld.lld` or `ld.gold` linker to perform optimization.

It is recommended to enable this flag, unless there is a need to debug the resulting binaries.

### minimal
When enabled, a `js` command (a JavaScript shell) won't be installed.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked libraries ???.

This flag should be disabled, unless there is an explicit need for static libraries.

### system-icu
Pass the `--with-system-icu` option to the configure script. Link against the `libicu` library that is provided by the external package, instead of using the one that comes prebundled with the `mozjs` tarball.

This flag should be enabled if the target system has the `libicu` library installed as it will help keeping it up to date and security patched, however can be disabled to avoid external dependency.

### test
Pass the `--enable-tests` option to the configure script. Disable an MPROTECT and a RANDMMAP PaX flags for `jsapi-tests` binary and execute a `make check` command after the main build is completed to run the test suite provided with a source code and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.
