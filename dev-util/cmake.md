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
Pass the `-DBUILD_QtDialog=ON` and option to the `cmake` command. Update an icon cache and an XDG database to pick up new launchers installed by CMake. Build and install a `cmake-gui` - QT-based graphical interface for CMake used to interactively configure project build settings.

It is safe to disable this flag.

### test
Pass the `-DBUILD_TESTING=yes` option to the `cmake` command. Execute the `bin/ctest` binary inside of the build directory when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers or developers.
