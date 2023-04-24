# app-arch/xz-utils

### doc
Pass the `--enable-doc` option to the configure script. Install additional documentation files into the `/usr/share/doc/xz-utils-<VERSION>` directory. This documentation consists of the list of authors, news, readme, thanks, todo list, frequently asked questions, XZ and LZMA file format description, etc.

It is safe to disable this flag.

### extra-filters
Does nothing when enabled and thus installing a complete set of encoders, decoders, matchers and checkers.

If disabled, Pass the `--enable-encoders=lzma1,lzma2`, `--enable-decoders=lzma1,lzma2`, `--enable-match-finders=hc3,hc4,bt4` and `--enable-checks=crc32,crc64` options to the configure script. Only enable a subset of `lzma1` and an `lzma2` encoders and decoders, an `hc3`, `hc4` and `bt4` matchers and a `crc32`, `crc64` checkers.

This flag can be disabled to minimize library size.

### nls
Pass the `--enable-nls` option to the configure script. Enable messages translation into different languages using Gettext library and install language files.

It is safe to disable the flag unless there is a need to use non-English languages.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `liblzma` library.

This flag can be safely disabled, unless there is an explicit need for static library.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
