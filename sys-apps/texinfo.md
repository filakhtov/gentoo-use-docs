# sys-apps/texinfo

### nls
Pass the `--enable-nls` option to the configure script. Enable an ability to translate programs messages into various languages based on the system locale using a Gettext library.

This flag should be enabled if there is a need to use non-English language.

### static
Append a `-static` option to the `LDFLAGS` variable for a duration of the build. Build and install a statically linked tools: `info`, `pod2texi`, `makeinfo`, etc.

The flag should only be enabled if there is a need for the static binaries.
