# dev-lang/spidermonkey

### custom-cflags
Normally, some aggressive options are removed from the `CFLAGS` variable while building the SpiderMonkey interpreter. Enabling this flag will pass through an optimization level set in the `CFLAGS` variable to the `--enable-optimize=` option that is written to the `.mozconfig` file to be used during the build.

This flag can be enabled to activate custom optimization level, however bug reports won't be accepted for such builds.

### custom-optimization
Normally, the SpiderMonkey interpreter is built without any compiler optimizations. Enabling this flag will ensure that an original `CFLAGS` variable will be passed as is when invoking a compiler during the build process.

This flag can be enabled to pass custom CFLAGS to the compiler, however bug reports won't be accepted for such builds.

### debug
Pass the `--enable-debug` option to the configure script. Build a JS engine with developer debug info, enable assertions to allow for easier debugging of linked programs.

This flag should be normally disabled as it has performance impact, can crash programs linked against the library and only useful for debugging.

### jit
Pass the `--enable-ion` option to the configure script. Enable the IonMonkey JavaScript JIT (Just-In-Time) compiler for SpiderMonkey - a whole-method JIT with the ability to perform type specialization, function inlining, linear-scan register allocation, dead code elimination and loop-invariant code motion.

This flag should be enabled for platforms that support JIT compilation to improve performance.

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
Pass the `--enable-tests` option to the configure script. Disable an MPROTECT and a RANDMMAP PaX flags for `jsapi-tests` binary and execute a `make check` command. Run test suite provided with a source code.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
