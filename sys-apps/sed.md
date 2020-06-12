# sys-apps/sed

### acl
Pass the `--enable-acl` option to the configure script. Enable ACL support for `sed` command, e.g. copy original file ACL permissions when doing an in-place file editing and creating a backup file.

It is recommended to modify this flag system-wide. If disabled while trying to edit file with ACL permissions set, these permissions can be lost.

### nls
Pass the `--enable-nls` option to the configure scrpit. Provide support for a program messages localization using gettext and install appropriate translation files.

This flag can be safely disabled as it is only needed for users who use a non-English system.

### selinux
Pass the `--with-selinux` option to the configure script. Provide an ability to copy a SELinux security context from an original file for `w` and `W` commands, when using `-i` (in-place) option with backup file and so forth.

This flag should only ever be changed system-wide by one of a SELinux-enabled Portage profiles.

### static
Append a `-static` option to a `LDFLAGS` variable to build a statically linked version of `sed`.

This flag should normally be disabled, unless there is a need for statically linked binary.
