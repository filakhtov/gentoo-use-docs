# sys-process/procps

### elogind
Pass the `--with-elogind` option to the configure script. Integrate with elogind to obtain additional information. Allow a `ps` command to display a login session, a session owner, and a display seat for running processes.

This flag should be enabled if there is a need to use elogind.

### kill
Pass the `--enable-kill` option to the configure script. Build and install a `kill` binary.

It is recommended to enable this flag as `procps` is a preferred provider of `kill` command for Gentoo distribution.

### modern-top
Pass the `--enable-modern-top` option to the configure script. Use "modern" settings for a `top` command when a `toprc` config doesn't exist. Change display colors, provide a graphical representation of a CPU load and change display formats.

It is safe to disable the flag.

### ncurses
Pass the `--with-ncruses` option to the configure script. Use an ncurses library for terminal handling to provide a `top`, a `slabtop` and a `watch` commands.

This flag can be disabled if there is no need for aforementioned commands.

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate programs messages into system locale using a Gettext library.

It is safe to disable this flag if there is no need to support non-English languages.

### selinux
Pass the `--enable-libselinux` option to the configure script. Provide an ability to obtain and display a SELinux context for running processes for `ps` command.

This flag should only ever be toggled system-wide, i.e. as part of the SELinux-enabled portage profile.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libprocps.a` library.

It is recommended to disable this flag unless there is an explicit need for a static library, e.g. for development purposes.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### systemd
Pass the `--with-systemd` option to the configure script. Integrate with SystemD to obtain additional information. Allow a `ps` command to display a login session, a session owner, a display seat, a parent container, a parent slice and a parent unit for running processes.

This flag should be enabled if the target system to be run with a SystemD ecosystem.

### test
Execute a `make check` command during a build. Run a test suite provided with a source code. This will extend a build time.

It is recommended to disable this flag as it is only useful for the Gentoo team, deveopers or testers.

### unicode
Pass the `--enable-watch8bit` option to the configure script. Enable support for Unicode characters for `watch` program.

This flag should normally be enabled as Unicode is widespread nowadays.
