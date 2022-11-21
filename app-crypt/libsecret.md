# app-crypt/libsecret

### crypt
Pass the `-Dgcrypt=true` option to the meson build script. Provide an ability to encrypt a D-Bus communication channel with the Secret Service using the `libgcrypt` library.

It is recommended to enable this flag.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc tool to generate and install the reference documentation describing the library API and exported symbols and providing usage examples.

It is safe to disable this flag.

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate the GIR metadata `Secret-1.gir` file during a build time to provide dynamic bindings for the `libsecret` library for languages other than C using the GObject introspection.

The flag can be safely disabled.

### test
Prepare a Python environment to properly run the tests. Start a new D-Bus session inside of the virtual Xvfb session and execute the `meson tests` command (using the tpm2 emulation if the `tpm` flag is enabled) inside of it to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disable as it is mainly useful for the maintainers, testers and developers.

### test-rust
This flag does nothing and should be disabled.

### tpm
Pass the `-Dtpm2=true` option to the meson build script. Provide an ability to encrypt and decrypt stored secrets using the TPM module (Trusted Platform Module), in addition to using the user's login password.

It is safe to disable this flag, but should be considered on platforms with TPM2 support for increased security.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `-Dvapi=true` option to the meson build script. Generate the `libsecret-1.vapi` Vala language bindings for the `libsecret` library.

It is safe to disable the flag.
