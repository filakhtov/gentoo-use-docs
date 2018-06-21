# app-misc/pax-utils
### caps
Pass the `USE_CAP=yes` variable to the `make` command. The `pspax` gains an ability to read capabilities of the processes. If disabled the `pspax` will always print `=` for a `CAPS` column for all processes.

It is safe to disable this flag.

### debug
Pass the `USE_DEBUG=yes` variable to the `make` command. Only works together with a `seccomp` flag. Use the `SCMP_ACT_TRAP` action instead of the `SCMP_ACT_KILL` if seccomp filter is violated and display exact syscall that has failed.

The flag can be safely disabled unless there is a need to debug PaX utils.

### python
Pass the `USE_PYTHON=yes` variable to the `make` command. This will install a `lddtree.py` script instead of a `lddtree.sh`. A `lddtree.py` is backwards compatible with a `lddtree.sh` but provides some extra features.

This flag can be safely disabled.

### seccomp
Pass the `USE_SECCOMP=yes` variable to the `make` command. Enable syscalls filtering using a `seccomp` (secure computing mode). Kernel support is required to use the `seccomp`, however it is provided by all modern Kernels.

This is security feature and generally should be enabled.
