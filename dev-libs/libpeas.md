# dev-libs/libpeas

### glade
Pass the `-Dglade-catalog=true` (`false` if the flag is disabled) option to the meson build command. Install the `libpeas-gtk.xml` Glade catalog file to provide an ability to use the libpeas widgets in Glade UI designer.

It is safe to disable the flag.

### gtk
Pass the `-Dwidgetry=true` (`false` when the flag is disabled) option to the meson build command. Build and install the `libpeas-gtk` library that provides a GTK+ user interface widget that can be used to manage plugins, i.e. load or unload them, and see some pieces of information.

This flag should be enabled if there is a need for plugin management UI.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the `Gtk-Doc` tool to generate and install the API reference documentation for the `libpeas` library.

It is safe to disable this flag.

### lua
Pass the `-Dlua51=enabled` option to the meson build command. Build and install the `liblua51loader` library - a LUA loader to provide support for plugins written using the LUA scripting language.

This flag should be enabled if there is a need to run LUA based plugins.

### luajit
This flag only works together with the `lua` flag. Pass the `-Dluajit=enabled` flag to the meson build command. Use the LuaJIT (LUA Just-In-Time Compiler) interpreter instead of standard one.

It is recommended to enable this flag on platforms that support JIT compilation.

### python
Prepare environment for the configure script to find an appropriate version of the Python interpreter. Pass the `-Dpython3=true` option to the meson build command. Build and install the `libpython3loader` library - a Python 3 loader to provide support for pluggins written using the Python scripting language.

This flag should be enabled if there is a need to run Python based plugins.

### test
Start a new Xvfb session and execute the `meson test` command inside of it after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend a build time.

This flag should be disabled as it is primarily useful for maintainers, testers or developers.

### vala
Pass the `-Dvapi=true` option to the meson build command. Generate and install the `libpeas-1.0.vapi` (and `libpeas-gtk-1.0.vapi` if the `gtk` flag is enabled) Vala language bindings for `libpeas` libraries.

It is safe to disable this flag.
