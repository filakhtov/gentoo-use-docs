# sys-devel/make

### guile
Pass the `--with-guile` option to the configure script. Provide a `guile` make function. Enable support for running `Makefile`s written using a Guile scheme programming language.

This flag is only ever necessary if target system to be using `Makefile`s written using a Guile, otherwise it is completely safe to disable.

### nls
Pass the `--enable-nls` option to the configure script. Enable localization support using gettext tools and install translations for program messages.

This flag should be enabled if there is a need to use non-English language, otherwise it is safe to disable.

### static
Append a `-static` option to the `LDFLAGS` variable during linking. Build and install statically linked `gmake` and `automake` binaries.

This flag should be disabled unless there is an explicit need for static binaries.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
