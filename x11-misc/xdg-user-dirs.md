# x11-misc/xdg-user-dirs

### gtk
Pull in the [x11-misc/xdg-user-dirs-gtk](../x11-misc/xdg-user-dirs-gtk.md) package as a dependency - a companion to `xdg-user-dirs` that integrates it into
the GNOME-based desktop environment and Gtk+ applications, and does two things when the user logs in: tracks changes of locale and prompts the user to localize directory names and creates a default gtk bookmarks file if there is none, based on a set of xdg user dirs.

This flag should be enabled for GNOME-based desktop environments.
