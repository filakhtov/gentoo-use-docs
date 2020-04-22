# dev-libs/totem-pl-parser

### archive
Pass the `-Denable-libarchive=yes` (`no` if the flag is disabled) option to the meson build command. Use the `libarchive` library to detect media discs in ISO files, e.g. DVD video, VCD, Bluray, etc.

This flag can be safely disabled, unless there is a need to access ISO images of media disks.

### crypt
Pass the `-Denable-libgcrypt=yes` (`no` when the flag is disabled) option to the meson build command. Use the `libgcrypt` library to decrypt Amazon XSPF playlists to support AmazonMP3 download files.

It is safe to disable the flag.

### gtk-doc
Pass the `-Denable-gtk-doc=true` option to the meson build command. Use the `Gtk-Doc` tool to generate and install the API library reference for the `libtotem-plparser` library in the HTML format.

It is safe to disable the flag.

### introspection
Pass the `-Dintrospection=true` (`false` if the flag is disabled) option to the meson build command. Generate and install the `TotemPlParser-1.0.gir` GIR metadata file to provide dynamic bindings for the `libtotem-plparser` library to languages other than C using the GObject Introspection framework.

The flag can be safely disabled.

### quvi
Pass the `-Denable-quvi=yes` (`no` when the flag is disabled) option to the meson build command. Use the `libquvi` library to provide an ability to parse video links and network playlists, to access media from online video sites and media streaming services, such as YouTube.

It is safe to disable the flag if there is no need to use online video libraries.

### test
Start a session D-Bus instance using the `dbus-launch` command and execut the `meson test` command inside of it from the build directory after the main build is completed to the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should be disabled as it is primarily oriented towards the Gentoo team, testers and developers.
