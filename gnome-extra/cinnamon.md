# gnome-extra/cinnamon

### gstreamer
Pass the `-Dbuild_recorder=true` option to the `meson` build script. Build and install the `cinnamon-recorder` binary - a Cinnamon built-in screen recording utility.

It is safe to disable this flag.

### gtk-doc
Pass the `-Ddocs=true` option to the configure script. Use the Gtk-Doc tool to generate documentation in the HTLM format and install it into system.

This flag can be safely disabled.

### networkmanager
Pass a `-Ddisable_networkmanager=false` (`true` if this flag is disabled) option to the `meson` build script. Build and install a `network@cinnamon.org` Cinnamon applet that is based on a NetworkManager's nm-applet to provide network management UI.

It is safe to disable the flag.

### nls
Pull in a [gnome-extra/cinnamon-translations](../gnome-extra/cinnamon-translations.md) package as a dependency to provide translations for Cinnamon desktop environment.

This flag should be enabled if there is a need to use Cinnamon in a non-English language.

