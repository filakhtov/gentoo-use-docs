# net-libs/nghttp2

### debug
Pass the `-DENABLE_DEBUG=true` option to the cmake command. Enable debugging build that activates extended logging at runtime and provides an ability to register debugging callbacks for different improtant lifecycle events.

This flag should only ever be enabled for debugging purposes as it has a significant performance impact.

### hpack-tools
Pass the `-DENABLE_HPACK_TOOLS=true` and `-DCMAKE_DISABLE_FIND_PACKAGE_Jansson=OFF` options to the cmake command. Enable support for an HPACK header compression algorithm for efficiently representing HTTP header fields, to be used in HTTP/2. It eliminates redundant header fields, limits vulnerability to known security attacks, and has a bounded memory requirement for use in constrained environments.

It is safe to disable the flag.

### jemalloc
Pass the `-DWITH_JEMALLOC=true` option to the cmake command. Replace the default memory allocator with one provided by the `jemalloc` library to mitigate heap fragmentation in long running server programs.

This flag should be enabled if the library to be used for server applications.

### static-libs
Pass the `-DENABLE_STATIC_LIB=true` option to the cmake command. Build and install a statically linked version of the `libnghttp2` library.

This flag should only be enabled if there is an explicit need for the static library.

### systemd
Pass the `-DCMAKE_DISABLE_FIND_PACKAGE_Systemd=OFF` option to the cmake command. This allow `nghttpx` to send a `READY=1` startup notification message to the systemd process via the `sd_notify()` call when it is ready to accept connections. It is useful when starting `nghttpx` through the systemd unit and allows to use the `Type=notify` service option.

This flag should only be enabled if there is a need to use `nghttpx` proxy on a systemd-enabled system.

### test
Pass the `-DCMAKE_DISABLE_FIND_PACKAGE_CUnit=OFF` option to the cmake command to build a test suite provided with the source code. Run the tests using the CUnit runner when the main build is completed to check for any regressions. This will extend the build time.

This flag should be normally disabled, because it is mainly useful for the Gentoo team, testers and developers.

### utils
Pass the `-DENABLE_APP=true` option to the cmake command. Build and install tools in addition to library: the `nghttp` - a simple HTTP/2 client, the `nghttpd` - a simple HTTP/2 server, the `nghttpx` - a reverse proxy for HTTP/2 and HTTP/1, and the `h2load` - a benchmarking tool for HTTP/2 servers.

It is safe to disable the flag.

### xml
This flag only makes sense if the `utils` flag is enabled. Pass the `-DWITH_LIBXML2=true` option to the cmake command. Use the `libxml2` library to provide an ability to get linked assets from the downloaded resource in `nghttp` client using the `-a` runtime option.

It is safe to disable the flag.
