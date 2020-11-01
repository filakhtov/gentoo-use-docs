# x11-misc/xdg-utils

### dbus
Pull in the [sys-apps/dbus](../sys-apps/dbus) package as a dependency. Allow detecting the GNOME desktop environment to properly handle various actions in xdg tools (`xdg-desktop-icon`, `xdg-desktop-menu`, etc) and provide an ability to inhibit, uninhibit, activate, lock and otherwise manipulate the screensaver using the `xdg-screensaver` tool.

It is recommended enabling this flag if there is a need to use the `xdg-screensaver` tool, otherwise it can be safely disabled.

### gnome
Pull in additional dependencies to provide `Net::DBus` and `X11::Protocols` Perl modules that will be used by the `xdg-screensaver` utility to properly inhibit the GNOME screensaver by simulating user activity, because simply calling the `dbus-send` command doesn't work, since `gnome-screensaver` watches the pid of the calling process and `dbus-send` exits immediately.

This flag should only be enabled on the systems that use GNOME screensaver.

### doc
Generate additional documentation in the HTML format using the xmlto tool and install it into the `/usr/share/doc/xdg-utils-<VERSION>/html` directory. Documentation contains the list of installed XDG commands, their description, list of options they support and a meaning of each option.

It is safe to disable the flag.

### perl
Pull in the [dev-perl/File-MimeInfo](../dev-perl/File-MimeInfo.md) package to enable the xdg-open utility to use XDG MIME Applications without a desktop environment. Trying to run the xdg-open tool with this flag disabled from outside of the DE will fall back to using the file util which does not implement the XDG standard.

This flag should be enabled if there is a need to invoke XDG MIME Applications via the xdg-open util outside of the DE.
