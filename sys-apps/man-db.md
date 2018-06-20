# sys-apps/man-db
### berkdb
Passes the `--with-db=db` option to the configure script, but only if a  `gdbm` flag is disabled. This will utilize the Berkeley DB database implementation for storing cache data.

This flag is safe to disable. This flag should not be enabled if a `gdbm` flag is enabled. If disabled GNU dbm will be used instead.

### gdbm
Passes the `--with-db=gdbm` option to the configure script. Uses the GDBM (aka GNU dbm) database implementation for storing cache data. This flag takes precedence over `berkdb` and is enabled by default anyway if both the `gdbm` and the `berkdb` flags are disabled.

It is recommended to enable this flag.

### manpager
Pulls in the [app-text/manpager](../app-text/manpager.md) package as a dependency to enable man pages colorization.

This flag can be safely disabled.

### nls
The flag passes the `--enable-nls` option to the configure script. Uses gettext to translate output messages into different languages, and provides input and output in localized formats. For example input prompts, command usages, etc can be displayed in languages other than English.

It is safe to disable this flag, unless there is a desire for non-English language output and input handling.

### selinux
Pulls in [sec-policy/selinux-mandb](../sec-policy/selinux-mandb.md) package as a dependency to enable proper operation of `mandb` command under the SELinux hardened Kernel.

This flag should only be enabled systemwide via a SELinux-enabled Portage profile.

### static-libs
Passes the `--enable-static` option to the configure script. This will produce statically linked libraries.

The flag should normally be disabled unless there is a need for statically linked libraries, e.g. for a development or other purposes.

### zlib
Exports `ac_cv_lib_z_gzopen=yes` into an environment. The variable is read by the configure script and enables zlib compression support by `mandb`. This will eliminate a need for temporary files creation when dealing with zlib compressed files.

It is safe to disable this flag.
