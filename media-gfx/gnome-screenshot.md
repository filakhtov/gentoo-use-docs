# media-gfx/gnome-screenshot

### X
Pass the `-Dx11=true` option to the meson build script. Enable support for the "fallback" X11 backend, which allows to take screenshots directly from the running X Window server, outside of the Gnome Shell environment.

This flag can be safely disabled if running GNOME desktop environment, but is required for other desktop environments that do not use Gnome Shell.
