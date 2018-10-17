# dev-libs/totem-pl-parser

### archive
Pass the `--enable-libarchive` option to the configure script. Use the `libarchive` library to detect media discs in ISO files, e.g. DVD video, VCD, Bluray, etc.
 
This flag can be safely disabled, unless there is a need to access ISO images of media disks.

### crypt
Pass the `--enable-libgcrypt` option to the configure script. Use the `libgcrypt` library to decrypt Amazon XSPF playlists to support AmazonMP3 download files.

It is safe to disable the flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `TotemPlParser-1.0.gir` GIR metadata file to provide dynamic bindings for the `libtotem-plparser` library to languages other than C using the GObject Introspection framework.

The flag can be safely disabled.

### quvi
Pass the `--enable-quvi` option to the configure script. Use the `libquvi` library to provide an ability to parse video links and network playlists, to access media from online video sites and media streaming services, such as YouTube.

It is safe to disable the flag if there is no need to use online video libraries.

### test
Start a session D-Bus instance using the `dbus-launch` command and execut the `make check` command inside of it after the main build is completed. Run the test suite provided with the source code to check for any regressions. This will extend a build time.

This flag should be disabled as it is primarily oriented towards the Gentoo team, testers and developers.
