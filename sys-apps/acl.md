# sys-apps/acl

### nls
Pass the `--enable-gettext` option to the configure script. Use a Gettext library to translate programs messages and a library output into various languages based on the system locale settings.

This flag should be enabled if there is a need to use any non-English languages.

### static-libs
Pass the `--enable-static` option to the configure script. When disabled, remove all statically linked files. Build and install a statically linked version of the `libacl` library.

The flag should only be enabled if there is a need for the static library.
