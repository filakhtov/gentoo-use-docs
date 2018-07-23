# sys-apps/attr

### nls
Pass the `--enable-gettext` option to the configure script. Use Gettext to provide an ability to translate programs messages and library output into various languages based on the system locale settings.

This flag should be enabled if there is a need to use a non-English language.

### static-libs
Pass the `--enable-static` option to the configure script. When disabled, remove all statically linked libraries before installing. Build and install a statically linked version of the `libattr` library.

The flag should only be enabled if there is a need for the static library.
