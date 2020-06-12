# sys-apps/texinfo

### nls
Pass the `--enable-nls` option to the configure script. Enable an ability to translate programs messages into various languages based on the system locale using a Gettext library.

This flag should be enabled if there is a need to use non-English language.

### standalone
Pass the `--without-external-libintl-perl`, `--without-external-Unicode-EastAsianWidth`, `--without-external-Text-Unidecode`, `--disable-perl-xs` options to the configure script. Build a Texinfo version that does not depend on external Perl packages.

This flag should normally be disabled.

### static
Append a `-static` option to the `LDFLAGS` variable for a duration of the build. Build and install a statically linked tools: `info`, `pod2texi`, `makeinfo`, etc.

The flag should only be enabled if there is a need for the static binaries.
