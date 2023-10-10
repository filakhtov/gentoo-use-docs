# media-video/wireplumber

### elogind
Pass the `-Delogind=enabled` option to the meson build script. Use the elogind daemon instead of the systemd-logind.

This flag should only be enabled system-wide as part of the Portage profile.

### system-service
Pass the `-Dsystemd-system-service=true` option to the meson build script. Install a system-wide systemd service for WirePlumber.

This flag should normally be disabled. It is only useful in very exceptional circumstances, such as on embedded systems.

### systemd
Pass the `-Dsystemd=enabled` and `-Dsystemd-user-service=true` options to the meson build script. Enable integration with logind and install systemd user unit files to activate WirePlumber on a per-user session.

This flag should be enabled system-wide on the systems that use systemd as their init daemon.

### test
Pass the `-Dtests=true` and `-Ddbus-tests=true` options to the meson build script. Run the `meson test` command after the main build is completed to execute the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
