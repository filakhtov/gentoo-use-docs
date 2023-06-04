# gnome-extra/cinnamon-session

### systemd
Cinnamon session depends on logind so this flag will pull in [sys-apps/systemd](../sys-apps/systemd.md) pacakge to satisfy that dependency. When disabled, pull in [sys-auth/elogind](../sys-auth/elogind.md) package instead and make sure that a `policykit` flag is set for it.

This flag should be enabled if the target system runs a SystemD as an init daemon.
