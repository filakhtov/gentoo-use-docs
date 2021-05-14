# sys-fs/e2fsprogs

### cron
Pass the `--with-cron-dir=/etc/cron.d` option to the configure script. Install the cron job that periodically runs `e2scrub` tool on all LVM volumes that are formatted in ext2, ext3 or ext4 filesystem to perform online filesystem check and either mark them as clean and update last checked timestamp or mark them for subsequent check during next mount.

This flag can be enabled if there is a need to perform automatic filesystem check.

### fuse
Pass the `--enable-fuse2fs` option to the configure script. Build and install `fuse2fs` tool for userspace handling of ext2/3/4 filesystems. This is mostly useful for non-Linux UNIX-like OSes that don't have a native EXT filesystem support but have a FUSE support.

It is recommended to disable this flag because native Kernel ext4 handling is way more efficient than FUSE.

### lto
Pass the `--enable-lto` option to the configure script. Append the `-flto` and `-ffat-lto-objects` options to `CFLAGS` and `LDFLAGS` for the duration of the build. Perform Link-Time Optimization (LTO) when building binaries and libraries.

It is recommended to enable this flag on a supported system with modern compiler.

### nls
Pass the `--enable-nls` option to the configure script. Use gettext to translate various program messages, e.g. help texts and interactive prompts.

This flag can be safely disabled unless there is a need to display messeages in languages other than English.

### split-usr
If the flag is enabled all produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Install statically linked libraries `*.a` (aka library archives) into the target system. If disabled these libraries will be removed from build tree before installation.

It is safe to disable the flag unless there is an explicit need for statically linked libraries, e.g. for development purposes.

### threads
Pass the `--with-pthread` option to the configure script. Use the `libpthread` library to enable support for using multiple thread in various tools, e.g. allow reading bitmap blocks in parallel and speed up `dumpe2fs`, `e2fsck` and `debugfs` tools for very large file systems.

This flag can be safely disabled.
