# sys-fs/fuse

### examples
Install additional examples, written in the C language, into the `/usr/share/doc/fuse-<VERSION>/examples` directory, including implementation of character device in userspace, ioctl handling, sample FUSE implementation.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libfuse` and `libulockmgr` libraries.

This flag should only be enabled if there is an explicit need for the static libraries.
