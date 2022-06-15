# x11-libs/pango

### debug
Append the `-DPANGO_ENABLE_DEBUG` (`-DG_DISABLE_CAST_CHECKS` if the flag is disabled) option to the CFLAGS environment variable for the duration of the build. Enable various debugging facilities and casting checks.

This flag should normally be disabled on production systems.

### introspection
Pass the `-Dintrospection=enabled` option to the meson build command. Generate and install the `Pango-1.0.gir`, `PangoCairo-1.0.gir`, `PangoFT2-1.0.gir` and, if the `X` flag is enabled, then `PangoXft-1.0.gir` GIR metadata files to provide dynamic bindings support for languages other than C using the GObject Introspection.

It is safe to disable this flag.

### sysprof
Pass the `-Dsysprof=enabled` option to the meson build script. Enable tracing support via the sysprof tool, e.g. send profiling information for `FcFontSetMatch`, `FcFontSetSort`, `FcInit` and other operations.

This flag should only be enabled if there is a need to use sysprof tool to profile font rendering.

### test
Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### X
Pass the `-Dxft=enabled` option to the meson build script. Enable support for rendering fonts using the Xft (X FreeType) backend.

This flag should be enabled on systems that run the X Window System.
