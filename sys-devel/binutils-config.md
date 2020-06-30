# sys-devel/binutils-config

### native-symlinks
Pass the `USE_NATIVE_LINKS=yes` (`no` if the flag is disabled) variable to the make command. This will instruct the `binutils-config` command to create "native" (unprefixed) symlinks, such as `ar` and `as`, pointing to their CTARGET counterparts, such as `x86_64-pc-linux-gnu-ar` and `x86_64-pc-linux-gnu-as` when switching toolchain versions.

It is recommended to enable this flag, otherwise many tools might not be able to find these binaries.
