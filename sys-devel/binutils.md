# sys-devel/binutils

### cet
Pass the `--enable-cet` option to the configure script. Remove the `-minidirect-branch` options from the `XXFLAGS` environment variables for the duration of the build. Enable support for CET (Intel's Control-Flow Enforcement Technology) - the Intel feature for helping prevent ROP (Return-Oriented Programming) and COP/JOP (Call/Jump Oriented Programming) style attacks via indirect branch tracking and a shadow stack.

It is safe to disable this flag, however it will be beneficial to enable it on compatible systems for improved security.

### debuginfod
Pass the `--with-debuginfod` option to the configure script. Use the `libdebuginfod` library to allow `objdump` and `readelf` tools to automatically query the `debuginfod` server over HTTP protocol to obtain separate DWARF/ELF debug files when they can not otherwise be found.

This flag can be safely disabled.

### doc
Run `make info` during a build to produce info pages. They will be installed into a `/usr/share/doc/binutils-<VERSION>` directory.

It is safe to disable this flag.

### gold
Pass the `--enable-gold` option to the configure script. Build and install the `ld.gold` linker - a faster replacement for a default `ld.bfd` that doesn't use BFD library for processing object files, and is especially useful for large C++ applications. Note that this linker can only process object file formats into the ELF (Executable Linux Format) binary format. The `ld.bfd` linker will still be used by default.

This flag should normally be enabled together with the `default-gold` flag to use faster linker implementation.

### gprofng
Pass the `--enable-gprofng` option to the configure script. Build and install a new GNU profiler - `gprofng`, which is designed as a replacement for `gprof` and better suited to work with modern applications.

This flag should normally be disabled.

### hardened
Pass the `--enable-texrel-check=error` (instead of `warning`) and `--enable-default-execstack=no` options to the configure script. Build a security hardened version of binutils. Firstly, prevent the linker from automatically assuming and marking the stack as executable for objects built from the assembler code that is missing the `.note.GNU-stack` section. Secondly, fail the build when trying to include non-PIC (Position-Independent Code) object into the shared library.

It is recommended to enable this flag, however doing so might break certain applications.

### multitarget
Pass the `--enable-targets=all` and `--enable-64-bit-bfd` options to the configure script. Provide a 64-bit computing support (also on hosts with narrower word sizes) and enable all supported targets (not only natively supported targets) for cross-compiling.

This flag can safely be disabled unless there is a need for cross-compiling.

### nls
Pass the `--without-included-gettext` option to the configure script when flag is enabled and the `--disable-nls` when it is disabled. Enable translation of program messages and help texts using gettext.

This flag should be enabled if there is a need for non-English CLI messages, otherwise it is safe to disable.

### pgo
Pass the `--enable-pgo-build=lto` option to the configure script. Enable PGO (Profile Guided Optimization) and LTO (Link Time Optimization) when building binutils. This produces a more performant binaries with the tradeoff of taking longer to build.

It is recommended to enable this flag to improve performance.

### plugins
Pass the `--enable-plugins` option to the configure script. Enable a plugin support provided by the `--plugin` runtime option for the linker tools, such as LLVM plugin.

This flag should be enabled if there is a need to support binutils plugins, e.g. gold.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked versions of binutils libraries, e.g. `libbfd.a`. When disabled `.la` files will be removed from installation.

It is recommended to disable this flag unless there is a need for static libraries, e.g. for specific development purposes.

### vanilla
When this flag is disabled, a set of additional patches, that include some Gentoo-specific fixes and enhancements, are applied to the source code prior to building the package. If this flag enabled, the aforementioned patches won't be applied and "vanilla" upstream sources will be used to build the binaries and libraries instead, and this might result in an unexpected behavior on a Gentoo system.

This flag should be disabled, unless there is an explicit need for unpatched version, e.g. when reporting the bug to an upstream.

### test
Execute `make -k check` after the build is complete. Run test suites provided with a source code. This will extend a build time.

This flag should normally be disabled as it is only useful for the Gentoo team, developers and testers.

### zstd
Pass the `--with-zstd` option to the configure script. Enable support for Zstd compressed debug sections for the `objcopy` tool (via both `--decompress-debug-sections` and `--compress-debug-sections=zstd`), as well as for the `addr2line` and `objdump --dwarf` commands.

This flag should only be enabled if there is a need to deal with zstd-compressed debug sections.
