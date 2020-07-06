# dev-libs/json-c

### cpu-flags-x86-rdrand
Pass the `-DENABLE_RDRAND=true` option to the cmake command. Provide an ability to generate random numbers using the `RDRAND` instruction using the on-chip hardware number generator. JSON-C library requires random numbers for hashing object field keys.

This flag should normally be disabled, especially because it is known to cause issues on some Ryzen-based systems.

### doc
Pass the `-DBUILD_DOCUMENTATION=true` option to the cmake command. Use the Doxygen tool to generate the documentation in the HTML format from the annotations in the source files and install it into the system.

It is safe to disable the flag.

### static-libs
Pass the `-DBUILD_STATIC_LIBS=true` option to the cmake command. Build and install a statically linked version of the `libjson-c` library.

This flag should normally be disabled, unless there is an explicit need for the static library.

### threads
Pass the `-DENABLE_THREADING=true` option to the cmake command. json-c library does not have a full multi-threaded support, however when this flag is enabled some code will be built to help make its use in threaded programs a bit safer, by using atomic operations for some functions. This, however has some significant performance impact (at least 3x times according to some sources).

This flag should normally be disabled, unless there is a need to use multi-threaded apps that use json-c and need its atomic operations.
