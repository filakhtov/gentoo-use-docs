# media-libs/openjpeg

### doc
Pass the `-DBUILD_DOC=ON` (`OFF` when disabled) option to the `cmake` command. Use the Doxygen tool to generate the low-level OpenJPEG and OpenJPIP (an implementation of JPEG 2000 Part9: Interactivity tools, APIs and protocols) C API documentation in the HTML format and install it into the `/usr/share/doc/openjpeg-<VERSION>` directory.

It is safe to disable the flag.

### static-libs
Pass the `-DBUILD_STATIC_LIBS=yes` (`no` when the flag is disabled) option to the `cmake` command. Build a statically linked version of the `libopenjp2` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Download additional test data files and extract it into the appropriate location to the source directory. Pass the `-DBUILD_TESTING=true` (`false` when disabled) option to the `cmake` command. Append the `-ffp-contract=off` option to various compiler flag variables (`CFLAGS`, `CXXFLAGS`, etc) for the duration of the build to disable fixed-point optimizations and avoid test failures due to fragile test cases. Execute the `ctest` command when the main build is completed to run the regression test suite provided with the source code. If there are any failures, check against a list of known failing tests and ignore these, then report and fail build if there are any unexpected results. This will extend the build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers, and it disables fixed point arithmetic optimizations that provide performance improvements.
