# dev-libs/boost

### context
Does nothing when enabled. When disabled, pass the `--without-context`, the `--without-coroutine` and the `--without-fiber` options to the bjam build script and remove include relevant C++ headers: a `/usr/include/boost/context/`, a `/usr/include/boost/coroutine/`, a `/usr/include/boost/coroutine2/` and a `/usr/include/boost/asio/spawn.hpp`. Provide a boost.context support for cooperative multitasking on a single thread.

It is safe to disable this flag unless there is a need to use boost contexts.

### debug
Change build target to a `gentoodebug` from a default `gentoorelease` one. This will produce boost libraries with debugging symbols attached.

This flag should normally be disabled, unless there is a need for debugging libraries, e.g. for development purposes or troubleshooting.

### doc
Install additional documentation files (including docs in an HTML format) into a `/usr/share/doc/boost-<VERSION>` directory.

It is safe to disable this flag.

### icu
Pass the `-sICU_PATH` option with a location of `libicu` files to the bjam build script. If disabled, pass the `--disable-icu` and the `boost.locale.icu=off` options to the bjam build script. Use a `libicu` library as a localization handling backend for Boost.Locale instead of alternative ones: a standard C++ library, a POSIX 2008 C library or a Win32 API.

This flag can be safely disabled, especially when localization is not necessary, however this will limit features.

### mpi
Append a `using mpi;` option to the `user-config.jam` configuration file for bjam build tool. If a `python` flag is also enabled build and install an `mpi` Python module for all supported targets. When disabled, pass a `--without-mpi` option to the bjam build script. Provide an alternative C++ interface to MPI with better support for modern C++ idioms - `Boost.MPI`.

It is safe to disable this flag unless there is a need to run or build applications dependent on Boost.MPI.

### nls
Does nothing when enabled. When disabled, pass a `--without-locale` option to the bjam build script and remove `locale` related include files, i.e. `/usr/include/boost/locale`. Disable support for `Boost.Locale` related features.

This flag is safe to disable if there is no need for a localization support via boost.

### python
Append a `using python;` option to the `user-config.jam` configuration file for bjam build tool. Pass the `--python-buildid` option to the bjam build script. If disabled, pass `--without-python` option to the bjam build script. Build and install `Boost.Python` modules - interoperability layer between Python and C++ code that allows to rapidly create Python bindings for arbitrary C++ code.

It is safe to disable this flag. It is only necessary for Python bindings development purposes.

### static-libs
Append a `static` value ot the `link` option passed to the bjam build script. Build and install statically linked boost libraries.

This flag can be safely disabled, unless there is a need for static libraries, e.g. for development purposes.

### threads
Create symlinks with a `-mt` suffix for all installed libraries (to indicate that they're multi-threaded variant). When disabled, pass the `--without-thread` option to the bjam build script. Build and install a `Boost.Thread` library for managing threads, data synchronization and copying data between threads.

This flag can be disabled if there is no need for threads support in the Boost library.

### tools
Run bjam build tool inside of the `tools` directory of the source tree. Build and install addidional tools: a `bcp`, `inspect`, `wave`, `auto_index` and `quickbook`.

It is safe to disable this flag.
