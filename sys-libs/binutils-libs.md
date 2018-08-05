# sys-libs/binutils-libs

### 64-bit-bfd
Pass the `--enable-64-bit-bfd` option to the configure script. This option is always passed on a bi-arch build. Provide a 64-bit computing support for built libraries. This is default on 64-bit targets, but is explicitly required to be turned on for hosts with narrower word sizes, e.g. when running a 32-bit OS on a 64-bit capable CPU.

This flag should normally be disabled, unless it is explicitly required.

### multitarget
Pass the `--enable-targets=all` and the `--enable-64-bit-bfd` options to the configure script. Provide a 64-bit support on hosts with narrower word sizes and enable all supported targets (not only natively supported targets) for cross-compiling.

This flag can safely be disabled unless there is a need for cross-compiling.

### nls
Pass the `--without-included-gettext` option to the configure script. If disabled, pass the `--disable-nls` option instead. Enable translation of program messages at runtime into various languages based on system locale settings using a system-provided version of the Gettext library.

This flag should only be enabled if there is a need to use non-English languages.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libopcodes` and the `libbfd` libraries. Note that a static `libiberty` library is always installed.

This flag should only be enabled if there is a need for the static libraries.
