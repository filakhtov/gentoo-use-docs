# dev-libs/libpcre

### bzip2
Pass the `--enable-pcregrep-libbz2` option to the configure script. Allow `pcregrep` utility to search for a pattern inside of BZip2 compressed files. Compression is handled by a `libbz2` library.

This flag can be safely disabled.

### cxx
Pass the `--enable-cpp` option to the configure script. Build and install a `libpcrecpp` library - a C++ wrapper library for `libpcre` that provides a nicer, object-oriented, namespaced interface.

It is recommended to enable this flag.

### jit
Pass the `--enable-jit` and the `--enable-pcregrep-jit` options to the configure script. Enable just-in-time compilation of regular expression patterns to improve performance. This option is not available for all the platforms.

It is recommended to enable this flag unless target platform does not support a JIT compilation.

### libedit
Pass the `--enable-pcretest-libedit` option to the configure script. Link a `pcretest` tool against a `libedit` library. Read terminal input using a `libedit` to provide line editing and history facilities.

This flag can be safely disabled.

### pcre16
Pass the `--enable-pcre16` option to the configure script. Build and install a library for 16-bit characters support. It is recommended to enable `unicode` flag together with this flag to support `UTF-16` encoding.

This flag can be safely disabled.

### pcre32
Pass the `--enable-pcre32` option to the configure script. Build and install a library for 32-bit characters support. It is recommended to enable `unicode` flag together with this flag to support `UTF-32` encoding.

This flag can be safely disabled.

### readline
Pass the `--enable-pcretest-libreadline` option to the configure script. Use a `libreadline` library to read input from terminal, enabling line editing support and history facilities for `pcretest` tool.

This flag can be safely disabled.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked libraries: a `libpcreposix.a`, a `libpcre.a` and if `cxx` flag is enabled then also a `libpcrecpp.a`.

This flag should normally be disabled unless there is an explicit need for static libraries, e.g. for development purposes.

### unicode
Pass the `--enable-utf` and the `--enable-unicode-properties` options to the configure script. Enable support for a UTF-8, UTF-16 and UTF-32 encodings. Internally these encodings will be translated to host byte order before processing.

It is recommended to enable this flag as Unicode character set is mainstream nowadays.

### valgrind
Pass the `--enable-valgrind` option to the configure script. Enable additional flags at compile time to better support running applications linked against `libpcre` library under the Valgrind profiler.

This flag should only ever be enabled if there is a need to profile apps linked with `libpcre` using Valgrind.

### zlib
Pass the `--enable-pcregrep-libz` option to the configure script. Allow `pcregrep` utility to search for a pattern inside of Gzip compressed files. Compression handling is managed by a `libz` library.

It is safe to disable this flag.
