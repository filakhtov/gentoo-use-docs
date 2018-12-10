# media-libs/grilo

### examples
Install example source code, written in C language into the `/usr/share/doc/grilo-<VERSION>/examples` directory. Examples are oriented towards developers and include displaying a list of browsable sources, YouTube plugin configuration, how to get content in an efficient way, how to load plugins and others.

It is safe to disable the flag.

### gtk
Pass the `--enable-test-ui` option to the configure script. Build and install the `grilo-test-ui` tool - a simple graphical user interface that is using GTK+ to allow users to perform queries and see their results.

This flag can be safely disabled.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `Grl-0.3.gir` and `GrlNet-0.3.gir` (also the `GrlPls-0.3.gir` if the `playlist` flag is enabled) GIR metadata files to provide dynamic bindings for the `libgrilo` and `libgrlnet` (also the `libgrlpls` when the `playlist` flag is enabled) libraries respectively to languages other than C, using the GObject Introspection framework. Note: a build will fail if the `network` flag is disabled.

It is safe to disable the flag.

### network
Pass the `--enable-grl-net` option to the configure script. Build and install the `libgrlnet` library that provides a thin wrapper on top of the `libsoup` library that is used by Grilo plugins for handling network connections over the HTTP protocol.

This flag should be enabled to provide network access for plugins that require it.

### playlist
Pass the `--enable-grl-pls` option to the configure script. Build and install the `libgrlpls` library that provides a wrapper on top of the `libtotem-plparser` library that provides an ability to parse media playlists and extract addresses of media objects.

This flag should be enabled to access media from playlist files.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run the test suite provided with the source code to check for regressions. This will extend the build time.

The flag should normally be disabled as it is mainly targeted for maintainers, testers and developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate the `grilo-0.3-custom.vala` (and `grilo-net-0.3-custom.vala` if the `network` flag is enabled) Vala language bindings for the `libgrilo` and `libgrlnet` libraries.

It is safe to disable this flag.
