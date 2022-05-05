# media-libs/libvmaf

### embed-models
Pass the `-Dbuilt_in_models=true` option to the Meson build script. Compile default VMAF models that are provided with the project into the library. If this flag is disabled consumers will be required to provide external training models before they can use the library.

It is recommended to enable this flag.

### test
Pass the `-Denable_tests=true` option to the Meson build script. Execute the `meson test` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, testers and maintainers.
