# gnome-extra/gnome-system-monitor

### systemd
Pass the `--enable-systemd` option to the configure script.

### X
Pass the `--enable-broken-wnck` option to the configure script. Use the `libwnck` library to obtain additional information about graphical processes, such as a display icon, an amount of X Server memory used by the application (i.e. `X Server Memory` column in the process list), etc.

This flag should normally be disabled, because this feature is unstable and causes `SEGFAULT`s.
