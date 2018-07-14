# dev-utils/cmake

### doc
Pass the `-DSPHINX_MAN=yes` and the `-DSPHINX_HTML=yes` options to a `cmake` command. Build an HTML and a MAN pages using sphinx Python documentation generator. Install additional HTML documentation into a `/usr/share/cmake-<VERSION>/html` directory.

This flag can be safely disabled.

### emacs
Compile and install Emacs major mode files for editing `CMake` sources. Provide syntax highlighting and indentation for `CMakeLists.txt` and `*.cmake` source files.

It is safe to disable the flag.

### ncurses
Pass the `-DBUILD_CursesDialog=yes` option to a `cmake` command. Build and install a `ccmake` - curses based user interface for CMake. Allow to interactively configure project build settings.

The flag can be safely disabled.

### qt5
Pass the `-DBUILD_QtDialog=ON` and the `-DCMAKE_DISABLE_FIND_PACKAGE_Qt5Widgets=ON` options to a `cmake` command. Update an icon cache and an XDG database to pick up new launchers installed by CMake. Build and install a `cmake-gui` - QT-based graphical interface for CMake used to interactively configure project build settings.

It is safe to disable this flag.

### server
Pass the `-DCMake_ENABLE_SERVER_MODE` and the `-DCMAKE_USE_LIBUV` options to a `cmake` command. Enable a server-mode for CMake (accessed via `-E server` runtime option). In this mode CMake starts a long running process that can provide semantic information about the code it executes to generate a buildsystem (in JSON format).

This flag can be safely disabled.

### system-jsoncpp
Pass the `-DCMAKE_USE_SYSTEM_LIBRARY_JSONCPP` option to a `cmake` command. Use a `JsonCpp` library provided by the system instead of internal CMake one. This might be useful if there are issues or vulnerabilities with included jsoncpp library and CMake haven't pulled an updated version yet.

It is safe to disable the flag. It is recommended to enable it if there are any other packages in the system that depend on [dev-libs/jsoncpp](../dev-libs/jsoncpp.md).

### test
Execute a `bin/ctest` binary inside of the build directory when the main build is complete. Execute a test suite provided with a source code. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.
