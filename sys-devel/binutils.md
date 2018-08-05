# sys-devel/binutils
### cxx
Pass the `--enable-gold` and `--enable-plugins` options to the configure script. Enable a plugin support provided by the `--plugin` runtime option for various tools. Build and install a `ld.gold` linker - a faster replacement for a `ld.bfd` that doesn't use BFD library for processing object files, especially useful for large C++ applications.

It is recommended to keep this flag on due to amount of applications in Portage that are written in C++.

### doc
Run `make info` during a build to produce info pages. They will be installed into a `/usr/share/doc/binutils-<VERSION>` directory.

It is safe to disable this flag.

### multitarget
Pass the `--enable-targets=all` and `--enable-64-bit-bfd` options to the configure script. Provide a 64-bit computing support (also on hosts with narrower word sizes) and enable all supported targets (not only natively supported targets) for cross-compiling.

This flag can safely be disabled unless there is a need for cross-compiling.

### nls
Pass the `--without-included-gettext` option to the configure script when flag is enabled and the `--disable-nls` when it is disabled. Enable translation of program messages and help texts using gettext.

This flag should be enabled if there is a need for non-English CLI messages, otherwise it is safe to disable.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked versions of binutils libraries, e.g. `libbfd.a`. When disabled `.la` files will be removed from installation.

It is recommended to disable this flag unless there is a need for static libraries, e.g. for specific development purposes.

### test
Execute `make -k check` after the build is complete. Run test suites provided with a source code. This will extend a build time.

This flag should normally be disabled as it is only useful for the Gentoo team, developers and testers.
