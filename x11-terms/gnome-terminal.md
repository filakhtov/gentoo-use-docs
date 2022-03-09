# x11-terms/gnome-terminal

### debug
Pass the `-Ddbg=true` option to the meson build script. Provide an ability to display extra debug messages, that will be produced by the terminal server (`gnome-terminal-server` daemon) and can be configured via the `GNOME_TERMINAL_DEBUG` environment variable. `GNOME_TERMINAL_DEBUG=help` can be used to get a list of all possible values.

This flag should only be enabled if there is a need to debug GNOME terminal emulator.

### gnome-shell
Pass the `-Dsearch_provider=true` option to the meson build script. Build and install a search provider for the GNOME Shell that provides an ability to find and focus a terminal window that contains a search phrase in the scroll buffer.

This flag can be safely disabled.

### nautilus
Pass the `-Dnautilus_extension=true` option to the meson build script. Build and install Nautilus plugin for GNOME terminal that allows to spawn a terminal emulator from any Nautilus window using the context menu.

It is safe to disable the flag.

### vanilla
Do not apply a Gentoo-specific patches. This is useful if there is a need to report bugs to upstream maintainer.

It is recommended to disable the flag.
