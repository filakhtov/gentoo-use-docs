# sys-devel/gcc
### altivec
Only available on PowerPC family of processors. Pass the `--enable-altivec` option to the configure script. Enable `AltiVec` operations and provide appropriate runtime options a `-maltivec` and a `-mabi=altivec`.

This flag should only be ever enabled on PowerPC platform with AltiVec support.

### cilk
Pass the `--enable-libcilkrts` option to the configure script. Only makes sense if a `cxx` flag is also enabled, because Intel Cilk Plus programming language is an extension to the C and C++ languages. It is deprecated as of 2018 in favor of the OpenMP.

This flag is safe to disable.

### cxx
Append `c++` to the `--enable-languages` option and pass the `--enable-libstdcxx-time` option to the configure script. When disabled pass the `--disable-build-with-cxx`, `--disable-build-poststage1-with-cxx` options to the configure script.

Enable support for the C++ programming language (compiler, linker, etc) when cross-compiling (for non-cross-compiling C++ is enabled regardless of this flag). Provide a `g++` tool.

This flag should be enabled because there are a lot of applications that depend on a C++ library and require a C++ compiler.

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
Does nothing when enabled. When disabled, however, pass the `--disable-libstdcxx-pch` option to the configure script. This option will avoid building the pre-compiled header (PCH) for libstdc++ that takes up a lot of space, and we have no use for it.

This flag is not recommended despite a performance gain it brings. See [gcc.gnu.org](https://gcc.gnu.org/wiki/PCHHaters) for details.

### pgo
Execute a `make profiledbootstrap` command during a build. Build the GCC with a PGO (profile guided optimization). This extends a build time because a bootstrap step can not be skipped and must be performed with profiling.

It is safe to disable the flag. Enabling it will give a ~7% performance increase at a compiler runtime.

### pie
Pass the `--enable-default-pie` option to the configure script. A resulting compiler will automatically pass a `-fPIE` option for all compilations and a `-pie` option for all linking steps.

This flag can be safely disabled, however PIE might be a useful security feature under the certain circumstances.

### regression-test
### sanitize
### ssp
### vanilla
### vtv
