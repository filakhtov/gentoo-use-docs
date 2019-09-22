# sys-apps/sed

### acl
Pass the `--enable-acl` option to the configure script. Enable ACL support for `sed` command, e.g. copy original file ACL permissions when doing an in-place file editing and creating a backup file.

It is recommended to modify this flag system-wide. If disabled while trying to edit file with ACL permissions set, these permissions can be lost.

### forced-sandbox
Modify a source code before compiling to force a sandbox mode that can't be disabled (normally enabled via the `--sandbox` command line option).

It is safe to disable this flag. It can be useful if there is a need to accept an untrusted input for sed, e.g. a web-service to validate sed expressions.

### nls
Pass the `--enable-nls` option to the configure scrpit. Provide support for a program messages localization using gettext and install appropriate translation files.

This flag can be safely disabled as it is only needed for users who use a non-English system.

### selinux
Export SELinux related variables for the configure script. Provide an ability to copy a SELinux security context from an original file for `w` and `W` commands.

This flag should only ever be changed system-wide by one of a SELinux-enabled Portage profiles.

### static
Append a `-static` option to a `LDFLAGS` variable to build a statically linked version of `sed`.

This flag should normally be disabled, unless there is a need for statically linked binary.
