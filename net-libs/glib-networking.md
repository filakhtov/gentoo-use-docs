# net-libs/glib-networking

### gnome
Pass the `--with-gnome-proxy` option to the configure script. Build and install a `libgiognomeproxy` library - a `GProxyResolverGnome` backend, that uses GSettings and the network proxy schemas from `gsettings-desktop-schemas` to provide proxy settings information.

This flag should be enabled if building glib-networking in a GNOME 3 environment.

### libproxy
Pass the `--with-libproxy` option to the configure script. Use a D-Bus service provided by the libproxy backend to provide PAC/WPAD auto-configuration support.

This flag should be enabled if there is a need to use proxy auto-configuration.

### ssl
Pass the `--with-gnutls` option to the configure script. Build and install a `libgiognutls` library - a GIO (GLib Input/Output) TLS backend that provides an ability to establish encrypted connections.

This flag should be enabled if there is a need to run applications that use glib-networking to establish TLS-encrypted connections.

### smartcard
Pass the `--with-pkcs11` option to the configure script. Build and install a `libgiopkcs11` library - a GIO (GLib Input/Output) PKCS#11 backend that provides an ability to access cryptographic tokens, such as hardware security modules (HSM) and smart cards.

This flag should be enabled if there is a need to deal with hardware cryptographic tokens.

### test
Start a new Xvfb session and execute a `make check` command inside of it when the main build is completed. Run a test suite provided with the source code to check against regressions. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
