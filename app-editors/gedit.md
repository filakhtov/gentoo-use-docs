# app-editors/gedit

### gtk-doc
Pass the `-Dgtk_doc=true` option to the configure script. Use the Gtk-Doc tool to generate an API reference documentation in the HTML format and install it into the `/usr/share/gtk-doc` directory.

This flag can be safely disabled if the developer documentation is not required.

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate and install the `Gedit-3.0.gir` and the `Gd-1.0.gir` GIR metadata files to provide dynamic bindings for the editor itself and the `libgd` library to languages other than C using the GObject Introspection infrastructure.

It is safe to disable the flag, however some Gedit plugins might require this.

### python
Pass the `-Dpython=true` option to the meson build script (this option is added by the custom Gentoo patch to allow building Gedit without support for Python plugins). Build support for the Python-based plugins and build some of the bundled plugins, e.g. quick open, Python console, external tools.

The flag can be safely disabled, however Python plugins won't be available.

### spell
Pass the `-Dspell=enabled` option to the meson build script. Use the gspell library to provide spell-checking features.

This flag should be enabled if there is a need for spell-checking.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=true` option to the meson build script. Provide an ability to use Gedit plugins written in Vala.

This flag should be enabled if there is a need to use or develop Vala plugins.
