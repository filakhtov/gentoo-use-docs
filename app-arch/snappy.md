# app-arch/snappy

### static-libs
This flag does not currently work, because an upstream maintainer removed static library support with build system update.

This flag should be disabled.

### test
Pass the `-DCMAKE_DISABLE_FIND_PACKAGE_GTest=false` option to the CMake command. Execute the `snappy_unittest` command when the main build is completed to run the test suite provided with the source code. This will extend a build time.

This flag should normally be enabled as these tests are mainly useful for the Gentoo team, testers or developers.
