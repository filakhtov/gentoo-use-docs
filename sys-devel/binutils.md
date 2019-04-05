# sys-devel/binutils

### cxx
Ensure that the `gold` and `plugins` flags are enabled in order to improve C++ code linking speed.

It is recommended to enable this flag as a lot of applications in Portage are written in C++.

### default-gold
Requires the `gold` flag to be enabled. Pass the `--enable-gold=default` option to the configure script. Ensure that the `ld.gold` linker is used by default, instead of the `ld.bfd` one, by installing it as the `ld` binary.

It is recommended to enable this flag to use the `ld.gold` linker by default, unless there is any specific reason not to.

### doc
Run `make info` during a build to produce info pages. They will be installed into a `/usr/share/doc/binutils-<VERSION>` directory.

It is safe to disable this flag.

### gold
Pass the `--enable-gold` option to the configure script. Build and install the `ld.gold` linker - a faster replacement for a default `ld.bfd` that doesn't use BFD library for processing object files, and is especially useful for large C++ applications. Note that this linker can only process object file formats into the ELF (Executable Linux Format) binary format. The `ld.bfd` linker will still be used by default.

This flag should normally be enabled together with the `default-gold` flag to use faster linker implementation.

### multitarget
Pass the `--enable-targets=all` and `--enable-64-bit-bfd` options to the configure script. Provide a 64-bit computing support (also on hosts with narrower word sizes) and enable all supported targets (not only natively supported targets) for cross-compiling.

This flag can safely be disabled unless there is a need for cross-compiling.

### nls
Pass the `--without-included-gettext` option to the configure script when flag is enabled and the `--disable-nls` when it is disabled. Enable translation of program messages and help texts using gettext.

This flag should be enabled if there is a need for non-English CLI messages, otherwise it is safe to disable.

### plugins
Pass the `--enable-plugins` option to the configure script. Enable a plugin support provided by the `--plugin` runtime option for the linker tools, such as LLVM plugin.

This flag should be enabled if there is a need to support binutils plugins, e.g. gold.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked versions of binutils libraries, e.g. `libbfd.a`. When disabled `.la` files will be removed from installation.

It is recommended to disable this flag unless there is a need for static libraries, e.g. for specific development purposes.

### test
Execute `make -k check` after the build is complete. Run test suites provided with a source code. This will extend a build time.

This flag should normally be disabled as it is only useful for the Gentoo team, developers and testers.
