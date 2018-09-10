# gnome-base/libglade

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libglade-2` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled. It is mainly targeted for the Gentoo team, testers and developers.

### tools
Build and install the `libglade-convert` tool - a small Python script used to convert old `.glade` files to the new format. When disabled, export the `am_cv_pathless_PYTHON=none` environment variable to prevent building the tool.

This flag should be enabled if there is a need to modernize old `.glade` files.
