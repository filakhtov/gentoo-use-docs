# sys-devel/gcc

### ada
Append `ada` to the `--enable-languages` option and pass it to the configure script. Execute the `make gnatlib-shared` command to build the Ada standard library followed by the `make gnattools` command to build the GNAT (GNU NYU Ada Translator) compiler and tools, then install them into the system.

This flag should only be enabled if there is a need for

### cet
Pass the `--enable-cet` option to the configure script. Enable support for Intel CET (Control-Flow Enforcement Technology) - a hardware assisted solution to help mitigate ROP (Return-Oriented Programming) and JOP (Jump-Oriented Programming) vulnerabilities.

This flag should only be enabled on compatible Intel platforms.

### custom-cflags
By default, when building GCC most of the custom flags are stripped out from the `CFLAGS` variable in order to avoid build failures related to over-zealous flags. When this flag is enabled, no flags will be stripped out.

This flag should only be enabled by experienced users who are confident that their flags aren't going to cause issues with the build.

### cxx
Append `c++` to the `--enable-languages` option and pass the `--enable-libstdcxx-time` option to the configure script. When disabled pass the `--disable-build-with-cxx`, `--disable-build-poststage1-with-cxx` options to the configure script.

Enable support for the C++ programming language (compiler, linker, etc) when cross-compiling (for non-cross-compiling C++ is enabled regardless of this flag). Provide a `g++` tool.

This flag should be enabled because there are a lot of applications that depend on a C++ library and require a C++ compiler.

### d
Append `d` to the `--enabled-languages` option that is passed to the configure script. Build and install a `gdc` binary - the GNU D Compiler, and a `libphobos` library - the D run-time library.

This flag can be safely disabled, unless there is a need for D language compiler.

### debug
Pass the `--enable-checking=yes` option to the configure script. The compiler is built to perform internal consistency checks. This does not change the generated code, but adds error checking within the compiler.

This flag should normally be disabled as it slows down the compiler.

### doc
Execute the `make doc-man-doxygen` during a build. Build and install a man page for a `libstdc++` library using a `doxygen` tool.

It is safe to disable the flag.

### fixed-point
Pass the `--enable-fixed-point` option to the configure script. This option is only useful for a MIPS architecture (otherwise it will fail a build). Enable a fixed-point arithmetic support for a C compiler.

The flag should only ever be enabled for MIPS architecture.

### fortran
Append a `f77,f95,fortran` values to the `--enable-languages` option passed to the configure script. When disabled pass the `--disable-libquadmath` option to the configure script, because only Fortran is using this library.

Enable support for Fortran (Fortran77, Fortran95 or latest supported Fortran version) programming language (compiler, linker, etc). Provide a `gfortran` or `g77` tool.

This flag can be safely disabled as it is only necessary for Fortran development.

### go
Requires a C++ compiler and will have no effect if the `cxx` flag is disabled (only possible while cross-compiling). Append `go` to the `--enable-languages` option passed to the configure script.

Enable support for Go programming language (compiler, linker, etc). Provide a `gccgo`, a `go` and a `gofmt` tools.

It is safe to disable this flag. It is only required for building Go application.

### graphite
Pass the `--with-isl` option to the configure script. Use an isl library for loop optimization in GCC Graphite framework. Provide a `-ftree-loop-linear`, a `-floop-strip-mine` and a `-floop-block` runtime options support.

This flag can be safely disabled.

### hardened
Enable additional security features like SSP/PIE/RELRO in the compilers by default. This might break various packages at a runtime or during an compilation.

This flag should normally be disabled and toggled only system-wide, e.g. by a hardened Portage profile.

### jit
Append `jit` to the `--enable-languages` option and passes the `--enable-host-shared` option to the configure script. Provide a `libgccjit` library that allows to create Just-In-Time compilers, e.g. from within interpreters.

This flag can be safely disabled.

### libssp
Pass the `--enable-libssp` option to the configure script. Use a `libssp` library for an SSP (Stack Smashing Protection) feature of a GCC. The SSP feature is provided by the C library on many target so that flag might be restricted.

It is recommended to enable this flag to provide a buffer overflow protection.

### lto
Pass the `--with-build-config=bootstrap-lto` option to the configuration script. Use the LTO (Link-Time optimization) when building the compiler toolchain itself.

It is recommended to enable this flag to optimize the compiler, however it is known to cause build issues in the past, so be wary.

### mpx
Pass the `--enable-libmpx` option to the configure script. Enabled an Intel® MPX (Memory Protection eXtension) support for the GCC. The MPX support is deprecated and has been removed from the GCC in version 9.1.

This flag should be disabled as it will be removed soon.

### multilib
Pass the `--enable-multilib` option and a list of supported ABIs via the `--with-multilib-list` option to the configure script. Provide an ability to compile both a 32-bit and a 64-bit libraries and binaries using the GCC.

This flag should only be ever toggled system-wide using Portage profile. Note: It is possible to switch from a multilib profile to a non-multilib but not the other way around.

### nls
Pass the `--enable-nls` and the `--without-included-gettext` options to the configure script. Enable program messages translation via gettext. An example of translated messages include a help text, compiler warnings and errors, etc.

It is safe to disable this flag unless there is a need for non-English program output.

### nptl
Pass the `--enable-tls` option to the configure script but only if target C library is a uClibc. Explicitly enable a TLS (Thread Local Storage) support that might not be properly detected when using a uClibc library.

This flag should normally be disabled.

### objc
Append an `objc` value to the `--enable-languages` option passed to the configure script. Enable support for an Objective-C programming language.

It is safe to disable this flag if there is no need to compile an Objective-C code with the GCC compiler.

### objc++
Requires C++ compiler and will have no effect if the `cxx` flag is disabled (only possible while cross-compiling). Append an `obj-c++` value to the `--enable-languages` option passed to the configure script. Enable support for an Objective-C++ programming language.

This flag can be safely disabled unless there is a need to compile an Objective-C++ code using the GCC compiler.

### objc-gc
Pass the `--enable-objc-gc` option to the configure script but only if the `objc` or the `objc++` flag is enabled too. An Objective-C runtime library is built using an external Boehm-Demers-Weiser garbage collector.

It is safe to disable the flag.

### openmp
Pass the `--enable-libgomp` option to the configure script. Build a `libgomp.so` library. Enable an OpenMP extension for the C/C++ and the Fortran languages via `-fopenmp` runtime option.

This flag is safe to disable.

### pch
Does nothing when enabled. When disabled, however, pass the `--disable-libstdcxx-pch` option to the configure script. This option will avoid building the pre-compiled header (PCH) for libstdc++ that takes up a lot of space, and there is no use for it.

This flag is not recommended despite a performance gain it brings. See [gcc.gnu.org](https://gcc.gnu.org/wiki/PCHHaters) for details.

### pgo
Execute a `make profiledbootstrap` command during a build. Build the GCC with a PGO (profile guided optimization). This extends a build time because a bootstrap step can not be skipped and must be performed with profiling.

It is safe to disable the flag. Enabling it will give a ~7% performance increase at a compiler runtime.

### pie
Pass the `--enable-default-pie` option to the configure script. A resulting compiler will automatically pass a `-fPIE` option for all compilations and a `-pie` option for all linking steps.

This flag can be safely disabled, however PIE might be a useful security feature under the certain circumstances.

### sanitize
Pass the `--enable-libsanitizer` option to the configure script. Enable an AddressSanitizer (aka ASan) - a fast memory error detector. Provide a `-fsanitize` family of runtime options and install a `libasan.so`, a `liblsan.so`, a `libtsan.so` and a `libubsan.so` libraries.

It is safe to disable the flag.

### ssp
Pass the `--enable-default-ssp` option to the configure script. Enable an SSP (stack smashing protection) feature by default. A resulting compiler will automatically use the `-fstack-protector-strong` option for all compilation processes. On platforms, where an SSP functionality is not provided by C library the `--enable-libssp` option will also be used regardless of the `libssp` flag state.

It is recommended to enable this flag due to security benefits it provides.

### systemtap
Pass the `--enable-systemtap` option to the configure script. Add a systemtap-style static marker to the debug hook function in the unwinder to enable GDB's (GNU Debugger) exception-handling code to work even in the absence of debuginfo.

This flag should only be enabled for debugging purposes.

### test
Install additional dependencies that will only be required to run the test suite provided with a source code. Execute a `make -k check` command to run the suite when build is finished. Copies test results into `/usr/share/doc/gcc-<VERSION>/testsuite` directory.

It is recommended to keep this flag disabled as it is only useful for the Gentoo team, developers and testers.

### valgrind
Pass the `--enable-valgrind-annotations` option to the configure script. Specify that the compiler should interact with the valgrind runtime, where selected invalid memory reads are marked as false positives and garbage collected memory is properly marked for proper interaction.

This flag should only be enabled by developers who are running GCC under the Valgrind instrumentation framework.

### vanilla
Skip applying any patches. This means hardening features like SSP, PIE and others won't be available.

This flag should be disabled.

### vtv
Pass the `--enable-vtable-verify` option to the configure script. Enable a vtable verification feature that causes libstdc++ to be built with its virtual calls in verifiable mode. Build and install a `libvtv.so` runtime library to support this feature. If disabled, pass the `--disable-libvtv` option to disable the feature.

It is recommended to enable this flag as it provides an additional safety net.

### zstd
Pass the `--with-zstd` option to the configure script. Enable support for Zstd-compressed LTO (Link Time Optimization) bytecode. Using Zstd in the tests by the GCC developers there were a little bit smaller LTO ELF (Executable Linux Format) files while being four to eight times faster than Zlib at compression and the decompression speed of Zstd in this use-case was comparable to Zlib.

It is safe to disable this flag.
