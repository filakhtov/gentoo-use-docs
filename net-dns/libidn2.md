# net-dns/libidn2

### nls
Pass the `--enable-nls` option to the configure script. Enable support for NLS (Native Language Support) to allow displaying informational, warning and error strings translated into the native language of the program's users, based on the system locale and configuration.

It is safe to disable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libidn2` library.

This flag should only be enabled if there is an explicit need for the static library.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
