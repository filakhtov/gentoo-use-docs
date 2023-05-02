# gnome-extra/cinnamon-session

### ipv6
Pass a `-Dipv6=true` option to a configure script. Define an `ENABLE_IPV6` macro that enables an IPv6 protocol support in underlying network libraries, e.g. when dealing with an XSMP (X Session Management Protocol).

This flag should be enabled if there is a need to run X session with Cinnamon over an IPv6 capable network.

### systemd
Cinnamon session depends on logind so this flag will pull in [sys-apps/systemd](../sys-apps/systemd.md) pacakge to satisfy that dependency. When disabled, pull in [sys-auth/elogind](../sys-auth/elogind.md) package instead and make sure that a `policykit` flag is set for it.

This flag should be enabled if the target system runs a SystemD as an init daemon.
