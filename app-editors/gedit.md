# app-editors/gedit

### gtk-doc
Pass the `-Dgtk_doc=true` option to the configure script. Use the Gtk-Doc tool to generate an API reference documentation in the HTML format and install it into the `/usr/share/gtk-doc` directory.

This flag can be safely disabled if the developer documentation is not required.

### python
Pass the `-Dpython=true` option to the meson build script (this option is added by the custom Gentoo patch to allow building Gedit without support for Python plugins). Build support for the Python-based plugins and build some of the bundled plugins, e.g. quick open, Python console, external tools.

The flag can be safely disabled, however Python plugins won't be available.
