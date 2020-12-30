# gnome-extra/cinnamon-screensaver

### systemd
The Cinnamon screensaver requires lodind daemon to work properly. Pull in the [sys-apps/systemd](../sys-apps/systemd.md) dependency to provide SystemD's logind when this flag is enabled. When disabled, pull in the [sys-auth/elogind](../sys-auth/elogind.md) package to use elogind instead.

This flag should be enabled if the target system uses the SystemD as an init daemon.

### xinerama
Pass the `-Dxinerama=true` option to the meson build script. Use the Xinerama X extension to query for multi-monitor geometry to properly display screensavers across multiple displays.

This flag should be enabled if the target system uses the Xinerama to manage multimonitor setup.
