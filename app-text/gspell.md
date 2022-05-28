# app-text/gspell

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `Gspell-1.gir` GIR metadata file to provide dynamic bindings for the `libgspell` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### test
Start a new D-Bus session inside of the virtual Xvfb session and execute the `make check` command inside of it when the main build is completed to run a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled. It is mainly targeted for the Gentoo team, testers and developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate `gspell-1.vapi` Vala language bindings for the `libgspell` library.

It is safe to disable the flag.
