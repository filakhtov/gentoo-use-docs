# sys-apps/smartmontools

### caps
Only works if the `daemon` flag is enabled. Pass the `--with-libcap-ng` option to the configure script. Enable the `-C` (`--capabilities`) option for `smartd` that uses the `libcap-ng` library to drop unneeded capabilities.

This flag should be enabled to improve security, but do note that mail sending won't work if capabilities are dropped.

### daemon
Build and install the `smartd` daemon that is used to monitor S.M.A.R.T. (Self-Monitoring, Analysis and Reporting Technology) status on storage drives and can be configured to send email warnings if problems are detected.

This flag can be safely disabled if there is no need for continuous drive status monitoring and reporting.

### selinux
Pass the `--with-selinux` option to the configure script. Use the `libselinux` library to provide an ability to run the smartmontools utilities under the SELinux-restricted kernel.

This flag should only ever be toggled system-wide.

### static
Append the `-static` option to the `LDFLAGS` for the duration of the build. Produce a statically linked binaries, both `smartd` and `smartctl`.

This flag should only ever be enabled if there is an explicit need for the static binaries.

### systemd
Pass the `--with-libsystemd` option to the configure script and pass the `--with-systemdsystemunitdir=` option pointing to the system directory with unit files. Use the `Type=notify` in the `smartd` unit file and enable the code that notifies SystemD when the daemon has fully started.

This flag should be enabled if the target system uses the systemd init system and the `daemon` flag is enabled.

### update-drivedb
Pass the `--with-gnupg` and `--with-update-smart-drivedb` options to the configure script. Install the initial drive database for smartmontools, the `update-smart-drivedb` script that is responsible for this database and a monthly cron job to do so automatically.

This flag can be disabled if there is no need for database updates, e.g. all current drives are already in the database and there is no plan to update hardware.
