# sys-apps/util-linux

### audit
Pass the `--with-audit` option to the configure script. Enable support for Kernel auditing in `login` and `hwclock` utilities. `login` will produce auditing messages on successful and failed login attempts, and `hwclock` will do so when the hardware clock is changed.

It is safe to disable this flag if no auditing support is necessary.

### build
This flag is used by Gentoo team when building and bootstrapping early stage images. Under the hood this flag will exclude [sys-apps/systemd](systemd.md) from dependencies regardless if `systemd` USE flag is set or not and force the `--without-udev` and `--without-systemd` options during the configure phase.

This flag should be disabled.

### caps
This passes `--enable-setpriv` option to configure script. This will build and install `setpriv` tool used to run programs with different set of privileges and capabilities.

No packages in Portage tree require `setpriv` and it is safe to disable this flag if there are no plans to use it directly.

### cramfs
This passes `--enable-cramfs` option to configure script. This option is responsible for building and installing `mkfs.cramfs` and `fsck.cramfs` tools that are responsible for dealing with compressed ROM file system.

This flag can be safely disabled, unless there is a need to manage cramfs.

### cryptsetup
Pass the `--with-cryptsetup` option to the configure script. Enable support in `libmount` for signed verity devices via the new `verity.roothashsig` option, which if provided, will make the kernel to verify that the root hash is signed by a key from the kernel keyring.

This flag can be safely disabled if there is no need to use signed verity devices.

### fdformat
This will pass `--enable-fdformat` option to configure script. This will build and install `fdformat` tool for low level formatting of a floppy disk.

It is safe to disable this flag, except when it is necessary to deal with floppy disks.

### hardlink
Pass the `--enable-hardlink` option to the configure script. Ensure that the `hardlink` program is built and installed. It traverses one or more directories searching for duplicate files. When it finds duplicate files, it uses one of them as the master, then removes all other duplicates and replaces them with a hardlink, pointing to the master file. This allows for conservation of disk space where multiple directories on a single filesystem contain many duplicate files.

This flag should normally be disabled and the program be used with extreme care.

### logger
Pass the `--enable-logger` option to the configure script to build and install the `logger` program. This program is used to write messages into the system log, and most oftenly used by various scripts to produce syslog entries.

It is safe to disable this flag.

### kill
This passes `--enable-kill` option to the configure script. This will build and install `kill` tool responsible for terminating a running process.

Multiple packages in Portage tree provide `kill` binary and therefore `kill` flag can't be enabled on more than one of them at a time.

### magic
Only works if the `ncurses` flag is enabled. Pass the `--with-libmagic` option to the configure script. Use the `libmagic` library to detect file type based on file signatures, aka "magic numbers" (or magic bytes), when trying to view the file contents using the `more` utility.

This flag can be safely disabled.

### ncurses
This flag will pass `--with-ncursesw` (if `unicode` flag is set too) or `--with-ncurses` (if `unicode` flag is disabled) to the configure script. If disabled `--without-tinfo` option will be passed instead.

This flag enables handling terminal output using ncurses library and colorized output for various tools (e.g. green header in `fdisk` or white background for current day in `cal`, etc).

This flag is safe to disable if colored output is not required.

### nls
This passes `--enable-nls` option to the configure script. As a result translation files will be processed and installed, allowing various tools to show localized messages and formats.

This flag can be safely disabled if the only language necessary is English.

### pam
This flag tells ebuild to compile and install `runuser` binary and associated configuration files for PAM subsystem: `runuser`, `runuser-l` and `su-1`.

`runuser` command can be used by root user to execute a process using privileges of different user and group. It is similar to `su` command but has slightly lower overhead, because only `session` PAM modules are executed, while `auth` and `account` ones are skipped.

No packages in Portage tree are dependent on `runuser` and therefore this flag can safely be disabled.

### python
Enables `--with-python` option for configure script. This will build and install `pylibmount.so` - a library that contains Python bindings for `libmount`, allowing Python scripts to retrieve and manipulate file-system mounting.

No packages in portage require this flag and it can be safely disabled, unless there is a need to use Python packages or scripts that depend on `libmount` bindings.

### readline
This flag will pass `--with-readline` option to configure script, enabling support for autocompletion, cursor movement and line editing capabilities for various tools (e.g. `fdisk`, `sfdisk`) that have interactive flows.

This flag can be disabled, but it will result degradation of usability in interactive tools.

### rtas
Export the `ac_cv_lib_rtas_rtas_get_sysparm=true` environment variable for the duration of the build. Enable support for RTAS (Run-Time Abstraction Services) calls which provide support for low-level system hardware configuration and operations, such as retrieving hardware sensor (temperature, fan speed, etc.) data, setting the operator panel LEDs, getting hardware error logs, injecting artificial hardware errors (for testing), getting VPD (Vital Product Data), and loading new firmware.

This flag is only relevant for PowerPC 64 platform.

### selinux
Enable `--with-selinux` option during configure. This will make sure that various tools behave properly with SElinux enabled. This includes access checking and reporting, manipulating contexts, etc.

This flag should only be enabled profile-wide and require support from Kernel.

### slang
Pass `--with-slang` option to configure script resulting in `cfdisk` using window management capabilities of `slang` for terminal output handling instead of `ncurses` library.

This flag results in the same set of capabilities being build for `cfdisk` as does enabling `ncurses`.

It is safe to disable this flag.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
This flag passes `--enable-static` option to configure. As a result static libraries will be built and installed.

This flag should only be set if such libraries are required, e.g. for development or as a dependency for other statically linked packages.

### suid
This flag responsible for passing `--enable-makeinstall-chown` and `--enable-makeinstall-setuid` options to configure. Doing so will instruct `make install` to set special permissions for several commands, so that they can be executed by regular users with elevated privileges (e.g. `mount`, `umount`).

It is required if user mounts for unprivileged users is desired.

### su
Pass the `--enable-su` option to the configure script. Build and install the `su` binary - which allow to run a command with substitute user and group ID and uses PAM for authentication, account and session management. This program is mostly designed for unprivileged users to gain elevated privileges.

It is safe to disable this flag if the `su` binary is not needed or is provided by a different package.

### systemd
Enable `--with-sytemd` and pass `--with-systemdsystemunitdir` options to configure script. This will extend behavior of various tools to support running from SystemD init system. It will also install `socket`, `service` and `timer` files for SystemD (e.g. `fstrim.timer` for periodic TRIM calls for SSD file-systems).

Enable this flag if system is using [sys-apps/systemd](systemd.md) as init daemon.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily useful for the developers, testers or maintainers.

### tty-helpers
This flag passes `--enable-mesg`, `--enable-wall` and `--enable-write` options to configure, resulting in `mesg`, `wall` and `write` binaries being built and installed.

It is recommended to keep this flag enabled as some Gentoo scripts are depending on these commands.

### udev
This passes `--with-udev` configure option. This will enable access to udev information for `findmnt` and `lsblk` tools allowing them to gather and display more data about block devices.

It is safe to disable this flag as no packages in Portage are dependent on it. However a requirement to obtain extended information should be considered first, before doing so.

### unicode
This flag passes `--enable-widechar` configure option. If `ncurses` flag is also set `--with-ncursesw` will be used instead of `--with-ncurses`. This flag enables "wide" character set support (aka multibyte, aka UTF-8). Commands like `dmesg`, `more` and others will benefit from this flag.

It can be safely disabled on systems that are only ever deal with English language.

### verify-sig
Decompress the upstream source code tarball and perform upstream signature verification before extracting it and building the package.

It is safe to disable this flag.
