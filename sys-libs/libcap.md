# sys-libs/libcap

### pam
Changes `Make.Rules` to set `PAM_CAP` to `yes`. This provides a `pam_cap` PAM module that allows to set inheritable capabilities for the current process.

This flag can be safely disabled.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
This flag ensures that `libcap.a` static library is installed into the target system.

This flag should normally be disabled unless there is a requirement to use static library, e.g. for development purposes.

### tools
Build and install the `captree` binary which allows to explore process runtime state and display the capability status of processes and their threads. This binary is written in Go language and requires Go to be built.

It is safe to disable this flag.
