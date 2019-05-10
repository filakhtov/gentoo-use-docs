# gnome-extra/gnome-system-monitor

### systemd
Pass the `-Dsystemd=true` (`false` when the flag is disabled) option to the meson build command. Use the `libsystemd` library to get additional information from the SystemD logind daemon and display which session, seat and unit a particular process belongs to.

It is safe to disable the flag and it should only be enabled on systems that uses SystemD logind or elogind.

### X
Pass the `-Dwnck=true` (`false` if the flag is disabled) option to the meson build command. Use the `libwnck` library to obtain additional information about graphical processes, such as a display icon, an amount of X Server memory used by the application (i.e. `X Server Memory` column in the process list), etc.

This flag should normally be disabled, because this feature is unstable and causes `SEGFAULT`s.
