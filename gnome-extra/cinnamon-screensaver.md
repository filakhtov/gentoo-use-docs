# gnome-extra/cinnamon-screensaver

### debug
Pass the `--enable-debug` option to the configure script. This option, however is not understood by the configure script.

This flag does nothing and should be disabled.

### doc
Pull in a number of dependencies that are necessary for building documentation, however does nothing more.

This flag should be disabled as it only pulls additional dependencies but is not actually using them.

### pam
Pull in the `virtual/pam` package as a dependency so that the configure script can detect and link against the PAM (Pluggable Authentication Modules) library. Provide an ability to use the PAM stack when unlocking the system and apply all the rules specified, e.g. two factor authentication or S/Key.

This flag should be enabled when integration with a PAM stack is desired.

### systemd
The Cinnamon screensaver requires lodind daemon to work properly. A SystemD's logind is used when this flag is enabled, and elogind is used instead if the flag is disabled.

This flag should be enabled if the target system uses the SystemD as an init daemon.

### xinerama
Pass the `--enable-xinerama` option to the configure script. Use the Xinerama X extension to query for multi-monitor geometry to properly display screensavers across multiple displays.

This flag should be enabled if the target system uses the Xinerama to manage multimonitor setup.
