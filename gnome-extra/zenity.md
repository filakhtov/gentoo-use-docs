# gnome-extra/zenity

### libnotify
Pass a `-Dlibnotify=true` option to the meson build script. Provide an ability to send desktop notifications via a `libnotify` library. Enable support for a `--notification`, `--text`, `--listen` and `--hint` runtime options.

This flag should be enabled if there is a need to send notifications via Zenity.

### webkit
Pass a `-Dwebkitgtk=true` option to the meson build script. Integrate with WebKitGTK+ rendering engine to display a WebView and HTML content inside of the spawned dialog. Enable support for a `--html`, `--no-interaction` and `--url` runtime options.

It is safe to disable this flag.
