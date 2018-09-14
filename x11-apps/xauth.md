# x11-apps/xauth

### ipv6
Pass the `--enable-ipv6` option to the configure script. Enable support for the IPv6 protocol to provide an ability to create Xautority entries for the IPv6 hosts.

This flag should only be enabled if there is a need to connect to a remote X server over the IPv6 protocol, e.g. via SSH forwarding.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code. This will extend a build time.

This flag should be normally disabled as it is mainly useful for the Gentoo team, testers or developers.
