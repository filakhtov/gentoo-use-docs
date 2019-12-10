# sys-libs/glibc

### audit
This flag only makes sense together with a `nscd` and a `selinux` flags. Export an `ac_cv_lib_audit_audit_log_user_avc_message=yes` (`no` if disabled) variable for the configure script, because there is no relevant configure option. Enable an ability to SELinux AVC denials via Kernel Audit Subsystem for a `nscd` daemon.

It is safe to disable the flag unless there is a need to use nscd under SELinux.

### caps
This flag only works if a `suid` flag is enabled or both a `nscd` and a `selinux` flags are enabled. Export an `ac_cv_lib_cap_cap_init=yes` variable to the configure script. A `pt_chown` command will drop unnecessary capabilities when run with suid flag and only preserve `CAP_CHOWN` and `CAP_FOWNER`. A `nscd` daemon will preserve capabilities necessary for using Audit Subsystem.

It is safe to disable this flag. It is recommended to keep it enabled if `suid` flag is enabled too.

### cet
Pass the `--enable-cet` option to the configure script. Enable support for Intel CET (Control-Flow Enforcement Technology) aims to defend against return-oriented programming (ROP) and call-jump-oriented programming (COP/JOP) attacks via a shadow stack to keep track of expected return addresses and to raise faults when the return addresses don't match up with what's found in the shadow stack. The Indirect branch tracking is for the stopping of jump/call oriented attacks.

This flag should only be enabled on supported CPUs.

### compile-locales
Normally, only locales that are specified in the `/etc/locale.gen` configuration file are generated after the package is installed. Enabling this flag will ignore the aforementioned config and generate all available locales. This will extend the build time and is generally used for building stage images and bootstrapping.

It is recommended to disable the flag.

### debug
This flag only makes sense if `hardened` flag is also enabled. Patch Makefile to allow core dump on SIGABRT signal on hardened systems or when debug mode is requested (append a `-DSSP_SMASH_DUMPS_CORE` option to the compiler flags when building an SSP source).

This flag can safely be disabled unless there is a need to debug application in regards to SSP, e.g. during development routines.

### doc
Execute `makeinfo` command to build additional documentation and install it into a `/usr/share/doc/glibc-<VERSION>/` directory.

It is safe to disable this flag.

### gd
Pass the `--with-gd` option to the configure script. Build and install a `memusagestat` - a utility to generate graphic (PNG images) from memory profiling data.

This flag can be safely disabled.

### hardened
Install a hardened Gentoo SSP and FORTIFY_SOURCE handlers. These handlers change an output produced during an application crash due to violation. Normally, a backtrace and a list of symbols is generated. When this flag is enabled an output is very terse - it only states that a crash happened.

This flag should only ever be toggled system-wide, e.g. as part of a Hardened Portage profile, because it has a lot of implications.

### headers-only
This flag only makes sense under the cross-compilation. When enabled ignores a [sys-devel/binutils](../sys-devel/binutils.md) and a [sys-devel/gcc](../sys-devel/gcc.md) dependencies, because they are provided by cross-compiler on the host system.

This flag should normally be disabled.

### multiarch
Enable the GNU indirect function support (IFUNC) - a feature that allows a developer to create multiple implementations of a given function and to select amongst them at runtime using a resolver function which is also written by the developer. The resolver function is called by the dynamic loader during early startup to resolve which of the implementations will be used by the application. Once an implementation choice is made it is fixed and may not be changed for the lifetime of the process.

This flag should be enabled for multi-architecture builds, e.g. if there is a need to run 32-bit apps in a 64-bit OS or when cross-compiling.

### multilib
Enable multilib support, e.g. both a 32-bit and a 64-bit libraries will be built and installed. This is usually necessary to run a 32-bit application on a 64-bit OS.

This flag should only be toggled system-wide, e.g. by multilib Portage profile as it requires tools that are capable of cross-compiling into different target.

### nscd
Pass the `--enable-nscd` option to the configure script. Build and install a `nscd` - name service cache daemon and associated init/service files.

It is generally safe to disable this flag, because `nscd` is primarily used for caching information from NIS or LDAP to avoid excessive queries for each UID/GID.

### profile
Pass the `--enable-profile` option to the configure script. Build and install additional set of libraries that can be used to generate profile information.

This flag can be safely disabled as it is only required for profiling applications, e.g. during development lifecycle.

### selinux
Pass the `--with-selinux` option to the configure script. Enable proper AVC denial handling for the `nscd` and provide an ability to set file contexts for the `makedb`.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### ssp
Pass the `--enable-stack-protector=all` (`no` when the flag is disabled) option to the configure script. Build all glibc libraries using the GCCs stack protection features to detect and prevent stack overruns.

It is recommended to enable this flag for improved protection, especially because it has minimal performance overhead.

### suid
Normally, a `pt_chown` binary has a SUID flag. It is necessary to manipulate permissions on a `/dev/pts` tree. When disabled SUID bit will be removed from binary.

This flag should be disabled because there are no permission issues on modern Linux systems with properly mounted `devpts`.

### systemtap
Pass the `--enable-systemtap` option to the configure script. Enable systemtap static probe points in C library to provide tracing support via SystemTap tool.

This flag should normally be disabled unless there is a need to trace C library and linked applications or collect benchmarking information.

### test
Execute the `make check` command for every enabled ABI after the main build is completed. Run the test suite provided with the source code to check for regressions. This will extend the build time.

These tests are mainly useful for maintainers and developers and the flag should normally be disabled for an average user.

### vanilla
When enabled Gentoo patches will not be applied to the source tree before compiling. Pass the `--enable-timezone-tools` option to the configure script. When disabled, these tools are provided by a [sys-libs/timezone-data](timezone-data.md) package.

This flag should be disabled.
