# net-libs/glib-networking

### gnome
Pass the `-Dgnome_proxy=enabled` (`disabled` if the flag is disabled) option to the meson build script. Build and install a `libgiognomeproxy` library - a `GProxyResolverGnome` backend, that uses GSettings and the network proxy schemas from `gsettings-desktop-schemas` to provide proxy settings information.

This flag should be enabled if building glib-networking in a GNOME 3 environment.

### libproxy
Pass the `-Dlibproxy=enabled` (`disabled` when the flag is disabled) option to the meson build script. Use a D-Bus service provided by the libproxy backend to provide PAC/WPAD auto-configuration support.

This flag should be enabled if there is a need to use proxy auto-configuration.

### ssl
Pull in the [app-misc/ca-certificates](../app-misc/ca-certificates.md) package as a dependency.

This flag should be enabled if there is a need to run applications that use the glib-networking to establish TLS-encrypted connections to public services.

### test
Start a new Xvfb session and execute the `meson test` command inside of it when the main build is completed. Run a test suite provided with the source code to check against regressions. This will extend a build time. When this flag is disabled patch the `meson.build` script to exclude the `tls/tests` directory in order to avoid installing the unnecessary [net-libs/gnutls](../net-libs/gnutls.md) dependency.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
