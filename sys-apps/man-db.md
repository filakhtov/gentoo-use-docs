# sys-apps/man-db

### manpager
Pulls in the [app-text/manpager](../app-text/manpager.md) package as a dependency to enable man pages colorization.

This flag can be safely disabled.

### nls
The flag passes the `--enable-nls` option to the configure script. Uses gettext to translate output messages into different languages, and provides input and output in localized formats. For example input prompts, command usages, etc can be displayed in languages other than English.

It is safe to disable this flag, unless there is a desire for non-English language output and input handling.

### seccomp
Pass the `--with-libseccomp` option to the configure script. Use the `libseccomp` library to confine most subprocesses that involve untrusted data handling.

This flag should normally be enabled as it provides security improvement.

### selinux
Pulls in [sec-policy/selinux-mandb](../sec-policy/selinux-mandb.md) package as a dependency to enable proper operation of `mandb` command under the SELinux hardened Kernel.

This flag should only be enabled systemwide via a SELinux-enabled Portage profile.

### static-libs
Passes the `--enable-static` option to the configure script. This will produce statically linked libraries.

The flag should normally be disabled unless there is a need for statically linked libraries, e.g. for a development or other purposes.

### zlib
Exports `ac_cv_lib_z_gzopen=yes` into an environment. The variable is read by the configure script and enables zlib compression support by `mandb`. This will eliminate a need for temporary files creation when dealing with zlib compressed files.

It is safe to disable this flag.
