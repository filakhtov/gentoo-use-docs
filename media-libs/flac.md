# media-libs/flac

### cxx
Pass the `--enable-cpplibs` option to the configure script. Build and install the `libFLAC++` library - a C++ object wrapper library around the `libFLAC` C library.

This flag should be enabled if there is a need to use FLAC library in a C++ application.

### debug
Pass the `--enable-debug` option to the configure script. Append the `-DDEBUG` option to the `CPPFLAGS` variable and `-g` option to the `CFLAGS` variable for the duration of the build. Build and install libraries and binaries with debugging symbols and enable runtime assertions. Print additional debugging information at runtime.

It is recommended to disable the flag, unless there is a need to debug the libraries or applications linked againts them.

### ogg
Pass the `--enable-ogg` option to the configure script. Allow the `libFLAC` library to store compressed FLAC data inside of the Ogg container to enable mixing several kinds of different streams, e.g. audio, data, metadata, etc.

This flag should be enabled if there is a need to encode and decode Ogg-wrapped FLAC audio.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libFLAC` library (and the `libFLAC++` if `cxx` flag is enabled).

This flag should only be enabled if there is an explicit need for the statically linked libraries.
