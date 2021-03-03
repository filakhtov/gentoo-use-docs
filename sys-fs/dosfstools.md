# sys-fs/dosfstools

### compat
Pass the `--enable-compat-symlinks` option to the configure script. Install symlinks for legacy names of the tools, i.e. the `dosfslabel`, `dosfsck`, `fsck.msdos`, `mkdosfs`, and `mkfs.msdos` symlinks will be created. The `fsck.vfat` and `mkfs.vfat` will be created regardless of this flag, see [Gentoo bug #584980](https://bugs.gentoo.org/584980) for details.

It is safe to disable the flag.

### iconv
Pass the `--with-iconv` option to the configure script. Use the `libiconv` library to convert strings from DOS codepage (default 437) to the current system's codepage, instead of using internal CP850 hardcoded table.

This flag should be enabled if there is a need to use devices containing file names and labels with non-ASCII characters, because internal table is fairly limited in its ability.

### test
Execute the `make check` command when the main build is completed. Run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly used by the Gentoo team, developers or testers.
