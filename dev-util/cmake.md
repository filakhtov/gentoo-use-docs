# dev-utils/cmake

### dap
Pass the `-DCMake_ENABLE_DEBUGGER=yes` option to the `cmake` command. Enable support for the DAP (Debugger Adapter Protocol) protocol and provide an ability to perform interactive step-debugging of cmake scripts.

It is safe to disable this flag.

### doc
Pass the `-DSPHINX_MAN=yes` and the `-DSPHINX_HTML=yes` options to a `cmake` command. Build an HTML and a MAN pages using sphinx Python documentation generator. Install additional HTML documentation into a `/usr/share/cmake-<VERSION>/html` directory.

This flag can be safely disabled.

### emacs
Compile and install Emacs major mode files for editing `CMake` sources. Provide syntax highlighting and indentation for `CMakeLists.txt` and `*.cmake` source files.

It is safe to disable the flag.

### gui
Pass the `-DBUILD_QtDialog=ON` and `-DCMake_QT_MAJOR_VERSION=5` options to the `cmake` command. Build and install a `cmake-gui` - QT-based graphical interface for CMake used to interactively configure project build settings. Update an icon cache and an XDG database to pick up new launchers installed by CMake.

It is safe to disable this flag.

### ncurses
Pass the `-DBUILD_CursesDialog=yes` option to a `cmake` command. Build and install a `ccmake` - curses based user interface for CMake. Allow to interactively configure project build settings.

The flag can be safely disabled.

### qt6
Only works if the `gui` flag is enabled. Pass the `-DCMake_QT_MAJOR_VERSION=6` (instead of 5) to the `cmake` cmake command. Use the QT6 library to build `cmake-gui` instead of QT5.

It is safe to disable this flag.

### test
Pass the `-DBUILD_TESTING=yes` option to the `cmake` command. Execute the `bin/ctest` binary inside of the build directory when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers or developers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
