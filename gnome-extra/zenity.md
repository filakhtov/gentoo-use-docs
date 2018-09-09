# gnome-extra/zenity

### debug
Pass a `--enable-debug=yes` option to a configure script. Change compiler flags to include debugging symbols into produced libraries and binaries and disable compiler optimizations.

This flag should only be enabled for debugging purposes.

### libnotify
Pass a `--enable-libnotify` option to a configure script. Provide an ability to send desktop notifications via a `libnotify` library. Enable support for a `--notification`, `--text`, `--listen` and `--hint` runtime options.

This flag should be enabled if there is a need to send notifications via Zenity.

### webkit
Pass a `--enable-webkitgtk` option to a configure script. Integrate with WebKitGTK+ rendering engine to display a WebView and HTML content inside of the spawned dialog. Enable support for a `--html`, `--no-interaction` and `--url` runtime options.
