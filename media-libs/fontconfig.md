# media-libs/fontconfig

### doc
Pass the `-Ddoc=enabled`, `-Ddoc-txt=enabled`, `-Ddoc-html=enabled`, `-Ddoc-man=enabled`, `-Ddoc-pdf=enabled` options to the meson build script. Generate documentation in various formats and manual pages from the source code instead of installing the prebuilt ones.

It is safe to disable the flag.

### nls
Pass the `-Dnls=enabled` option to the meson build script. Enable support for NLS (Native Language Support) to allow displaying informational, warning and error strings translated into the native language of the program's users, based on the system locale and configuration.

It is safe to disable this flag.

### test
Pass the `-Dtests=enabled` option to the meson build script to build the test suite provided with the source code, and execute the `meson test` command after the main build is completed to it and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
