# sys-fs/dosfstools

### udev
Pass the `--with-udev` option to the configure script. Use the `libudev` library to read additional device information like parent-child device relationship, if device is removable, etc from Udev.

It is recommended to enable this flag unless there is a need to save space and avoid Udev dependency.

### compat
Pass the `--with-compat-symlinks` option to the configure script. Install symlinks for legacy names of the tools, i.e. the `dosfslabel`, `dosfsck`, `fsck.msdos`, `mkdosfs`, and `mkfs.msdos` symlinks will be created. The `fsck.vfat` and `mkfs.vfat` will be created regardless of this flag, see [Gentoo bug #584980](https://bugs.gentoo.org/584980) for details.

It is safe to disable the flag.
