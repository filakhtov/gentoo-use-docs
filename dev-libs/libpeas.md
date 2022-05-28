# dev-libs/libpeas

### glade
Pass the `-Dglade-catalog=true` (`false` if the flag is disabled) option to the meson build command. Install the `libpeas-gtk.xml` Glade catalog file to provide an ability to use the libpeas widgets in Glade UI designer.

It is safe to disable the flag.

### gtk
Pass the `-Dwidgetry=true` (`false` when the flag is disabled) option to the meson build command. Build and install the `libpeas-gtk` library that provides a GTK+ user interface widget that can be used to manage plugins, i.e. load or unload them, and see some pieces of information.

This flag should be enabled if there is a need for plugin management UI.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build command. Use the `Gtk-Doc` tool to generate the API reference documentation in the HTML format for the `libpeas` library and install it into the `/usr/share/gtk-doc/html/libpeas` directory.

It is safe to disable this flag.

### lua
Pass the `-Dlua51=enabled` (or `-Dluajit=enabled` if the JIT target is enabled) option to the meson build command. Build and install the `liblua51loader` library - a LUA loader to provide support for plugins written using the LUA scripting language.

This flag should be enabled if there is a need to run LUA based plugins.

### python
Prepare environment for the configure script to find an appropriate version of the Python interpreter. Pass the `-Dpython3=true` option to the meson build command. Build and install the `libpython3loader` library - a Python 3 loader to provide support for pluggins written using the Python scripting language.

This flag should be enabled if there is a need to run Python based plugins.

### test
Start a new Xvfb session and execute the `meson test` command inside of it after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend a build time.

This flag should be disabled as it is primarily useful for maintainers, testers or developers.

### vala
Prepare environment with the appropriate version of vala runtime. Pass the `-Dvapi=true` option to the meson build command. Generate and install the `libpeas-1.0.vapi` (and `libpeas-gtk-1.0.vapi` if the `gtk` flag is enabled) Vala language bindings for `libpeas` libraries.

It is safe to disable this flag.
