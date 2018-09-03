# gnome-extra/cinnamon-session

### doc
Pass a `--enable-docbook-docs` option to a configure script. Generate and install D-Bus API documentation in an HTML format using the DocBook tool and install it into the `/usr/share/doc/cinnamon-session-<VERSION>` directory.

It is safe to disable the flag.

### ipv6
Pass a `--enable-ipv6` option to a configure script. Define an `ENABLE_IPV6` macro that enables an IPv6 protocol support in underlying network libraries, e.g. when dealing with an XSMP (X Session Management Protocol).

This flag should be enabled if there is a need to run X session with Cinnamon over an IPv6 capable network.

### systemd
Cinnamon session depends on logind so this flag will pull in [sys-apps/systemd](../sys-apps/systemd.md) pacakge to satisfy that dependency. When disabled, pull in [sys-auth/elogind](../sys-auth/elogind.md) package instead and make sure that a `policykit` flag is set for it.

This flag should be enabled if the target system runs a SystemD as an init daemon.
