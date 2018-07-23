# sys-apps/diffutils

### nls
Pass the `--enable-nls` option to the configure script. Use a Gettext library to provide an ability to translate programs messages into various languages based on the system locale.

This flag should be enabled if there is a need to use non-English languages.

### static
Append a `-static` option to the `LDFLAGS` variable for a duration of the build. Build and install statically linked binaries: `cmp`, `diff`, `diff3` and `sdiff`.

This flag should only be enabled if there is a need for the static binaries.
