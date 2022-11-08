# gui-libs/vte-common

### systemd
Pass the `-D_systemd=true` option to the Meson build script. Enable integration with systemd, in particular creating systemd scopes and associating the VTE processes with these scopes.

This flag should only be enabled on systems that use systemd init system.
