# x11-libs/pixman

### loongson2f
Pass the `-Dloongson-mmi=enabled` option to the meson build script. Enable inline assembly code that uses Loongson MMI (Loongson Multimedia Instructions) SIMD instruction set to improve image manipulation performance on the Loongson platform.

This flag should only be enabled on the Loongson platform.

### static-libs
Pass the `-Ddefault_library=both` (instead of the `shared` if the flag is disabled) option to the meson build script. Build a statically linked version of the `libpixman` library and install it together with the shared one.

It is recommended to keep this flag disabled, unless there is an explicit need for the static library.

### test
Pass the `-Dopenmp=enabled` option to the Meson build script. Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.
