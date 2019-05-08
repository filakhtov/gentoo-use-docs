# gnome-base/dconf

### gtk-doc
Pass the `-Dgtk_doc=true` (`false` if the flag is disabled) option to the meson configure command. Use the Gtk-Doc tool to extract source code annotations and generate documentation in the HTML format that will be installed into the `/usr/share/gtk-doc/html/dconf` directory.

It is safe to disable this flag since produced documentation is developer-centric.

### test
Start a new Xvfb session and execute a `ninja test` command inside of it. Run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled. It is primarily useful for the Gentoo team, testers and developers.
