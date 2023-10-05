# dev-lang/spidermonkey

### clang
Use the Clang compiler instead of GCC. Set the respective environment variables for all the build tools to ensure LLVM is used. Pass the `--enable-linker=lld` and `--enable-lto=cross` options to the configure script.

It is safe to disable this flag.

### debug
Pass the `--enable-debug` and `--disable-optimize` options to the configure script. Build a JS engine with developer debug info, enable assertions to allow for easier debugging of linked programs and disable various optimizations that can make debugging harder.

This flag should be normally disabled as it has performance impact, can crash programs linked against the library and only useful for debugging.

### jit
Pass the `--enable-jit` option to the configure script. Enable the IonMonkey JavaScript JIT (Just-In-Time) compiler for SpiderMonkey - a whole-method JIT with the ability to perform type specialization, function inlining, linear-scan register allocation, dead code elimination and loop-invariant code motion.

This flag should be enabled for platforms that support JIT compilation to improve performance.

### lto
Pass the `--enable-lto` option and `--enable-linker=lld`, if the `clang` flag is enabled, or `--enable-linkerd=gold`, if it is not, to the configure script. Enable link-time optimization (LTO) to run additional compiler routines to improve performance of the resulting binaries and libraries, however this will make it impossible to step through the code using the debugger. Requires `ld.lld` or `ld.gold` linker to perform optimization.

It is recommended to enable this flag, unless there is a need to debug the resulting binaries.

### test
Pass the `--enable-tests` option to the configure script. Disable an MPROTECT and a RANDMMAP PaX flags for `jsapi-tests` binary and execute a `make check` command after the main build is completed to run the test suite provided with a source code and check for any regressions. This will extend the build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.
