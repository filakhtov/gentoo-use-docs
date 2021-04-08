# media-libs/taglib

### boost
Pass the `-DCMAKE_DISABLE_FIND_PACKAGE_Boost=OFF` (`ON` if the flag is disabled) option to the `cmake` command. Use the Boost C++ libraries to perform atomic operations (if standard atomic operations aren't available) and endianness conversion. If the flag is disabled, the library will try to fallback to GCC-specific implementation if available, then try to use OS specific (MacOS, Windows) and so on, all the way down to its own "quick and dirty" implementation.

It is safe to disable the flag, however is recommended if there are no any alternative mechanisms, such as OS specific.

### debug
Build library with assertions enabled. When disabled, append the `-DNDEBUG` option to the `CPPFLAGS` for a duration of the build to disable them.

This flag should normally be disabled, unless there is a need to debug the library or develop against it.

### doc
Run the `cmake docs` command to build the documentation in HTML format from source code annotations using the Doxygen tool.

This flag can be safely disabled.

### examples
Pass the `-DBUILD_EXAMPLES=true` (`false` when the flag is disabled) to the `cmake` command. Build and install a set of small example programs that demonstrate the usega of the `libtag` libraries, including `tagreader` - to read and print tags from the media file; `tagreader_c` - same as `tagreader`, but written in C, instead of C++; `tagwriter` - writing tags into the media file; `framelist` - for identifying ID3v1, ID3v2 or APE tags and printing them; `strip-id3v1` - for removing any tags from the media file.

It is safe to disable the flag.

### test
Pass the `-DBUILD_TESTS=true` (`false` if the flag is disabled) to the `cmake` command. Build a test suite and run the `ninja check` command when the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled, as it is primarily oriented towards the developers, testers and maintainers.
