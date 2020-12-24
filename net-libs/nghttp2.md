# net-libs/nghttp2

### cxx
Pass the `--enable-asio-lib` option to the configure script. Build and install the `libnghttp2_asio` library - a C++ wrapper built on top of `libnghttp2` library that provides high level abstraction API to build HTTP/2 applications. It depends on `Boost::ASIO` and `OpenSSL` libraries and provides server and client side API.

It is safe to disable the flag, unless there is a need to use the library with Boost-based C++ applications.

### debug
Pass the `--enable-debug` option to the configure script. Enable debugging build that enables extended logging at runtime and provides an ability to register debugging callbacks for different improtant lifecycle events.

This flag should only ever be enabled for debugging purposes as it has a significant performance impact.

### hpack-tools
Pass the `--enable-hpack-tools` option to the configure script. Enable support for an HPACK header compression algorithm for efficiently representing HTTP header fields, to be used in HTTP/2. It eliminates redundant header fields, limits vulnerability to known security attacks, and has a bounded memory requirement for use in constrained environments.

It is safe to disable the flag.

### jemalloc
Pass the `--with-jemalloc` option to the configure script. Replace the default memory allocator with one provided by the `jemalloc` library to mitigate heap fragmentation in long running server programs.

This flag should be enabled if the library to be used for server applications.

### libressl
Use the LibreSSL library instead of the OpenSSL one for handling an HTTPS (Secure HTTP) communication.

This flag should be toggled system-wide, as both libraries can't be installed at the same time.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libnghttp2` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Execute the `make check` command after the main build is completed. Use the Cunit testing tool to run the test suite provided with the source code. This will extend a build time.

This flag should be normally disabled, because it is mainly useful for the Gentoo team, testers and developers.

### threads
Pass the `--enable-threads` option to the configure script. Use the pthreads library to provide threading support for variety of applications, including `nghttpd` and `h2load`. Make sure that library code is thread safe, e.g. appropriately initialize the OpenSSL library, handle signals, etc.

It is recommended to enable this flag.

### utils
Pass the `--enable-app` option to the configure script. Build and install tools in addition to library: the `nghttp` - a simple HTTP/2 client, the `nghttpd` - a simple HTTP/2 server, the `nghttpx` - a reverse proxy for HTTP/2, and HTTP/1, and the `h2load` - a benchmarking tool for HTTP/2 servers.

It is safe to disable the flag.

### xml
This flag only makes sense if the `utils` flag is enabled. Pass the `--with-libxml2` option to the configure script. Use the `libxml2` library to provide an ability to get linked assets from the downloaded resource in `nghttp` client using the `-a` runtime option.

It is safe to disable the flag.
