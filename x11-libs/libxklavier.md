# x11-libs/libxklavier

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the `Xkl-1.0.gir` GIR metada file and install it into the `/usr/share/gir-1.0` directory to provide an ability to dynamically generate bindings for languages other than C using the GObject Introspection.

The flag can be safely disabled.

### vala
This flag only works if the `introspection` flag is enabled. Prepare a build environment for Vala build so proper version can be found and used. Pass the `--enable-vala` option to the configure script. Generate the `libxklavier.vapi` file - Vala language bindings for the `libxklavier`.

It is safe to disable the flag.
