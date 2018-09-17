# dev-libs/libpeas

### glade
Pass the `--enable-glade-catalog` option to the configure script. Install the `libpeas-gtk.xml` Glade catalog file to provide an ability to use the libpeas widgets in Glade UI designer.

It is safe to disable the flag.

### gtk
Pass the `--enable-gtk` option to the configure script. Build and install the `libpeas-gtk` library that provides a GTK+ widget that can be used to manage plugins, i.e. load or unload them, and see some pieces of information.

This flag should be enabled if there is a need for plugin management UI.

### lua
Pass the `--enable-lua5.1` option to the configure script. Build and install the `liblua51loader` library - a LUA loader to provide support for plugins written using the LUA language.

This flag should be enabled if there is a need to run LUA based plugins.

### luajit
This flag only works together with the `lua` flag. Pass the `--enable-luajit` flag to the configure script. Use the LuaJIT (LUA Just-In-Time Compiler) interpreter instead of standard one.

It is recommended to enable this flag on platforms that support JIT compilation.

### python
Prepare environment for the configure script to find an appropriate version of the Python interpreter. Pass the `--enable-python3` option to the configure script. Build and install the `libpython3loader` library - a Python 3 loader to provide support for pluggins written using the Python language.

This flag should be enabled if there is a need to run Python based plugins.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed to run the test suite provided with the source code. This will extend a build time.

This flag should be disabled as it is primarily useful for the Gentoo team, testers or developers.
