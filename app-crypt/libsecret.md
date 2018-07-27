# app-crypt/libsecret

### crypt
Pass the `--enable-gcrypt` option to the configure script. Provide an ability to encrypt a D-Bus communication channel with the Secret Service using the `libgcrypt` library.

It is recommended to enable this flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate the GIR metadata `Secret-1.gir` file during a build time to provide dynamic bindings for the `libsecret` library for languages other than C using the GObject introspection.

The flag can be safely disabled.

### test
Prepare a Python environment to properly run the tests. Start a new Xvfb session and execute the `make check` command inside of it. Run a test suite provided with the source code. This will extend a build time.

This flag should normally be disable as it is mainly useful for the Gentoo team, testers and developers.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Generate the `libsecret-1.vapi` Vala language bindings for the libsecret `library`.

It is safe to disable the flag.
