# sys-libs/libcap

### pam
Changes `Make.Rules` to set `PAM_CAP` to `yes`. This provides a `pam_cap` PAM module that allows to set inheritable capabilities for the current process.

This flag can be safely disabled.

### static-libs
This flag ensures that `libcap.a` static library is installed into the target system.

This flag should normally be disabled unless there is a requirement to use static library, e.g. for development purposes.
