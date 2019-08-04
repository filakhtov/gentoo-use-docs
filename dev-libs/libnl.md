# dev-libs/libnl

### debug
Pass the `--enable-debug` option to the configure script. Enable various debugging statements that print an additional runtime debugging information to the stderr output when running a program that is linked against the `libnl` library.

This flag should normally be disabled, unless there is a need to debug the library itself or the program that's linked against it.

### python
Prepare the environment to use appropriate versions of the Python interpreter. Build and install the `netlink` Python module - a Python wrapper for netlink protocols for all enabled Python implementations.

It is safe to disable the flag, unless there is a need for the `netlink` Python module.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libnl-3`, `libnl-route-3`, `libnl-idiag-3`, `libnl-genl-3`, `libnl-nf-3`, `libnl-xfrm-3` libraries.

This flag should normally be disabled, unless there is an explicit need for these static libraries.

### threads
Pass the `--enable-threads` option to the configure script. When enabled, use the Posix threads for performing mutex locking, unlocking and obtaining read/write logs for concurrent operations. If disabled, locking functions will be replaced with simple endless loop shims and provide no concurrent execution.

It is recommended to enable this flag, especially if the `libnl` library to be used with application that uses threads.

### utils
Pass the `--enable-cli` option to the configure script. Build and install various utilities, such as `nf-exp-list`, `nf-ct-add`, `nf-log`, `nf-queue`, `nl-link-release` and bunch of others.

This flag can be safely disabled, unless there is a need to use one or more tools provided by the library.
