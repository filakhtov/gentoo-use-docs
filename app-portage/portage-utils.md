# app-portage/portage-utils

### nls
Pass a `NLS=yes` option to the make command. Use a Gettext library to translate programs messages into various languages based on the system locale settings.

The flag should be enabled if there is a need to use any non-English languages.

### static
Pass a `STATIC=yes` option to the make command to append `-static` option to the `LGFLAGS` variable. Build and install a statically linked version of binaries: `q`, `qlist`, `qsearch`, etc.

This flag should only be enabled if there is a need for static binaries.
