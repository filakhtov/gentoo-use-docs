# app-crypt/gcr

### debug
Pass the `--enable-debug=yes` (instead of `default`) option to the configure script. Turn off compiler optimization. Disable keyboard input grabbing by the password entry dialog so to allow switching to a different window and attaching a debugger.

This flag should only be enabled if there is a need to debug the gcr itself or applications that are linked against it.

### gtk
Pass the `--with-gtk` option to the configure script. Build and install the `gcr-viewer` - a certificate and key viewer written in GTK and the `gcr-prompter` - prompt dialog for crypto related UI tasks.

It is safe to disable the flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install GIR metadata `Gck-1.gir`, `Gcr-3.gir` (and `GcrUi-3.gir` if the `gtk` flag is enabled) files into the `/usr/share/gir-1.0` directory.

This flag can be safely disabled.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled. It is mainly targeted for the Gentoo team, testers and developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate `gck-1.vapi`, `gcr-3.vapi`, `pkcs11.vapi` (and `gcr-ui-3.vapi` if the `gtk` flag is enabled) Vala language bindings for gcr and gck libraries.

It is safe to disable this flag.
