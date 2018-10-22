# media-libs/openjpeg

### doc
Pass the `-DBUILD_DOC=ON` (`OFF` when disabled) option to the `cmake` command. Use the Doxygen tool to generate the low-level OpenJPEG and OpenJPIP (an implementation of JPEG 2000 Part9: Interactivity tools, APIs and protocols) C API documentation in the HTML format and install it into the `/usr/share/doc/openjpeg-<VERSION>` directory.

It is safe to disable the flag.

### static-libs
Execute the `cmake` command using a separate build directory to build a statically linked version of the `libopenjp2` library and then run the `cmake install` command from that same directory to install it.

This flag should only be enabled if there is an explicit need for the static library.

### test
Download additional test data files and extract it into the appropriate location to the source directory. Pass the `-DBUILD_TESTING=true` (`false` when disabled) option to the `cmake` command. Execute the `ctest` command when the main build is completed to run the regression test suite provided with the source code. If there are any failures, check against a list of known failing tests and ignore these, then report and fail build if there are any unexpected results. This will extend the build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
